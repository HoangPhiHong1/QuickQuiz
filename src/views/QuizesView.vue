<script setup>
  import q from "../data/quizes.json"
  import {ref, watch} from "vue"
  import Card from "../components/Card.vue"

  const quizes = ref(q)
  const search = ref("")
  
  watch (search, ()=>{
    quizes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()))
  })
  
</script>

<template>
  <div>
    <header>
      <h1>Quick Quiz</h1>
      <input v-model.trim="search" type="text" placeholder="Search...">
    </header>
    <div class="options-container">
      <Card v-for="quiz in quizes" :key="quiz.id" :quiz="quiz"/>
    </div>
  </div>
</template>

<style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Protest+Riot&display=swap');
  .container{
    max-width: 1000px;
    margin: 0 auto;
  }
  header{
    margin-bottom: 10px;
    margin-top: 30px;
    display: flex;
    align-items: center;
    
  }
  header h1 {
    font-weight: bold;
    margin-right: 30px;
    font-family: sans-serif;
    font-size: 100px;
    font-family: 'Protest Riot', sans-serif;
    color: #40A2E3;
  }
  header input{
    border: none;
    background-color: rgba(128, 128, 128, 0.1);
    padding: 10px;
    border-radius: 10px;
  }
  .options-container{
    display: flex;
    flex-wrap: wrap;
    margin-top: 40px;
  }
  /* CARD */
  .card{
    width: 310px;
    overflow: hidden;
    border-radius: 3%;
    box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.1);
    margin-bottom: 35px;
    margin-right: 20px;
    cursor: pointer;
  }
  .card img{
    width: 100%;
    height: 190px;
    margin: 0;
  }
  .card .card-text{
    padding: 0 0 5px 20px
  }
  .card .card-text h2{
    font-weight: bold;
  }
</style>