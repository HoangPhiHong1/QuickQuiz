<script setup>
    import { defineProps } from 'vue';

    const {questionStatus, barPercentage} = defineProps(["questionStatus","barPercentage"])
</script>

<template>
    <header>
        <h4>Question {{ questionStatus }}</h4>
        <div class="bar">
            <div class="completion" :style="{width: barPercentage}"></div>
        </div>
    </header>
</template>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Lilita+One&display=swap');
    header{
        margin-top: 20px;
        font-family: 'Lilita One', sans-serif;
    }
    header h4 {
        font-size: 30px;
    }
    .bar {
        width: 300px;
        height: 50px;
        border : 3px solid black;
    }
    .completion{
        height: 100%;
        width: 33%;
        background-color: #74E291;
    }
</style>