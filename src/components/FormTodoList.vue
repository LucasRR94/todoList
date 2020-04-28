<template>
  <div class="main-form">
    <div class="container-box">
        <div>
          <h3>New Todo Item:</h3>
        </div>
        <div class="main-inputs">
          <div class="main-content">
            <div>
              <input placeholder="Please type the content of todo item:" type="text" name="todocontent" v-model="contentTodo">
            </div>
            <div>
              <input placeholder="Please type the deadline of todo:" type="date" name="tododate" v-model="maxDateTodo">
            </div>
            <div>
              <input v-on:click="$emit('loadTodoItem',contentTodo,maxDateTodo)" type="submit" value="Adicionar">
            </div>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FormTodoList',
  data () {
    return {
      contentTodo: '',
      maxDateTodo: ''
    }
  }
}
</script>

<style scoped>
  *{
    font-family: 'Roboto', sans-serif;
    box-sizing: border-box;
    margin:0 0;
    padding:0 0;
  }
  .main-form{
    width:100vw;
    height:30vh;
  }
  .container-box{
    margin:1rem;
    width: 90%;
  }
  .container-box div h3{
    font-size:1rem;
  }
  .main-inputs{
    margin-top:0.2rem;
    border-radius: 1rem;
    border:5px solid rgb(30, 30, 30);
    height: 18vh;
  }
  .main-content{
    margin: 0.2rem 0.1rem;
    width: 85vw;
    height: 14vh;
    display: flex;
    flex:1;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .main-content div{
    margin:0.1rem 0rem;
    padding:0.1rem;
    border:none;
    border-radius: 0.2rem;
  }
  .main-inputs div input{
    color:white;
    background-color: black;
    font-size: 0.8rem;
    border:none;
    border-radius:0.1rem;
  }
  .main-inputs div input[type="text"]
  {
    width:70vw;
    text-align: left;
    padding:0rem 0.1rem;
  }
  .main-inputs div input[type="date"]{
    width:32vw;
    text-align: center;
  }
  .main-inputs div input[type="submit"]{
    width:20vw;
    height:4vh;
    border-radius: 0.2rem;
    text-align: center;
    padding:0.1rem 0.1rem;
  }
  @media(min-width:410px){
    .main-form{
      display: flex;
      flex:1;
      justify-content: center;
      width:100vw;
      height:32vh;
    }
    .container-box{
      margin:1rem;
      width: 90%;
      max-width: 500px;
    }
    .container-box div h3{
      font-size:1rem;
    }
    .main-inputs{
      margin-top:0.2rem;
      border-radius: 1rem;
      border:5px solid rgb(30, 30, 30);
      height: 20vh;
      display:flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
    .main-content{
      margin: 0.2rem 0.1rem;
      width: 85vw;
      max-width: 480px;
      height: 50vh;
      display: flex;
      flex:1;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
    .main-content div{
      border:none;
      border-radius: 0.2rem;
    }
    .main-inputs {
      height:22vh;
    }
    .main-inputs div input{
      color:white;
      background-color: black;
      font-size: max(1rem,14px);
      border:none;
      border-radius: 0.2rem;
    }
    .main-inputs div input[type="text"]
    {
      padding:0.1rem;
      max-width: 280px;
      width:70vw;
      text-align: left;
      padding:0rem 0.1rem;
      border-radius: 0.2rem;
    }
    .main-inputs div input[type="date"]{
      padding:0.1rem;
      width:38vw;
      max-width: 170px;
      text-align: center;
      border-radius: 0.2rem;
    }
    .main-inputs div input[type="submit"]{
      padding:0.1rem;
      width:20vw;
      max-width: 100px;
      border-radius: 0.2rem;
      text-align: center;
      padding:0.1rem 0.1rem;
      border-radius: 0.2rem;
    }
  }

</style>
