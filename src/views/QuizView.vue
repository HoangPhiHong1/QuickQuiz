<script setup>
    import Question from "../components/Question.vue"
    import QuizHeader from "../components/QuizHeader.vue"
    import Result from "../components/Result.vue"
    import {useRoute} from "vue-router"
    import quizes from "../data/quizes.json"
    import {ref, computed} from "vue"

    const route = useRoute()
    const quizId = parseInt(route.params.id)
    const quiz = quizes.find(q => q.id ===  quizId)
    const currentQuestionIndex = ref(0)
    const questionStatus = computed(() => {
        return `${currentQuestionIndex.value}/${quiz.questions.length}`
    })
    const barPercentage = computed(()=> {
        return `${currentQuestionIndex.value/quiz.questions.length * 100}%`
    })
    const numberOfCorrectAnswer =ref(0)
    const onOptionSelected = (isCorrect) =>{
        if(isCorrect){
            numberOfCorrectAnswer.value++;
        }

        if(quiz.questions.length - 1 === currentQuestionIndex.value){
            showResults.value = true;
        }

        currentQuestionIndex.value++
    }
    const showResults = ref(false)
</script>


<template>
    <div>
        <QuizHeader 
          :questionStatus = "questionStatus"
          :barPercentage = "barPercentage"  
        />
        <div>
            <Question 
            v-if = "!showResults"
            :question="quiz.questions[currentQuestionIndex]"
            @selectOption="onOptionSelected" 
            />
            <Result 
                v-else
                :quizQuestionLength = "quiz.questions.length"
                :numberOfCorrectAnswer = "numberOfCorrectAnswer"
            />
        </div>
        
    </div>
</template>