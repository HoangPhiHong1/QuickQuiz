<template>
  <div class="container">
    <header>
      <h1>Quizes</h1>
      <input type="text" placeholder="Search...">
    </header>
    <div class="options-container">
      <div class="card">
        <img src="https://shorturl.at/nG579" alt="Math picture">
        <div class="card-text">
          <h2>Math</h2>
          <p>3 questions</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
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
    font-size: 50px;
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