<script setup>
    import {defineProps, defineEmits} from "vue"

    const emit =  defineEmits(["selectOption"])

    const {question} = defineProps(['question'])

    const emitSelectedOption = (isCorrect) => {
        emit("selectOption", isCorrect)
    }
</script>


<template>
    <div class="question-container">
        <h1 class="question">{{ question.text }}</h1>
    </div>
    <div class="option-container">
        <div v-for="option in question.options" 
        :key="option.id" 
        class="option"
        @click="emitSelectedOption(option.isCorrect)"
        >
            <p class="option-label">{{ option.label }}</p>
            <div class="option-value">
                <p>{{ option.text }}</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Lilita+One&display=swap');
    .question-container{
        margin-top: 20px;
        font-family: 'Lilita One', sans-serif;
    }
    .question{
        font-size: 40px;
        margin-bottom: 20px;
    }
    .option {
        margin-bottom: 20px;
        cursor: pointer;
        display: flex;
        font-family: 'Lilita One', sans-serif;
    }
    .option-label{
        width: 50px;
        height: 50px;
        font-size: 30px;
        display: flex;
        align-items: center;
        justify-content: center;
        background-color: #BBE2EC;
    }
    .option-value{
        background-color: rgb(244,239,239);
        width: 100%;
        font-size: 30px;
        padding: 0 20px;
    }
</style>