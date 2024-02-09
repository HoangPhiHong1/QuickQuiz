<script setup>
    import {defineProps} from "vue"
    import {RouterLink} from "vue-router"
    const {quizQuestionLength,numberOfCorrectAnswer} = defineProps(["quizQuestionLength","numberOfCorrectAnswer"])
</script>

<template>
    <div class="results">
        <p>THE RESULT IS:</p>
        <h1>
            {{ numberOfCorrectAnswer }} / {{ quizQuestionLength }}
        </h1>
        <RouterLink to="/" style="font-size: 50px;">RETURN</RouterLink>
    </div>
    
</template>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Protest+Riot&display=swap');
    .results{
        text-align: center;
        padding: 100px 0;
        font-family: "Protest Riot", sans-serif;
    }
    p{
        font-size: 80px;
        color: #FDBF60;
    }
    h1{
        font-size: 120px;
        color: #FF8911;
    }
</style>