<template>
  <div class="main-todo">
    <transition-group name="effectDisplacement" tag="ul">
      <ul v-for="todo in newtodoItem" :key="todo.idTodoItem">
          <li>
            <div class="main-item" key="todo.idTodoItem">
              <div class="item-todo">
                <div class="title-todo">
                    <h4>To do Item</h4>
                </div>
                <div class="content">
                    <span>To do: </span>
                    <span class="task-class">{{todo.content}}</span>
                </div>
                <div class="deadLine">
                  <span>Deadline: </span>
                  <span class="deadline-class">{{todo.deadLine}}</span>
                </div>
              </div>
              <button v-on:click="$emit('delTodoItem', todo.idTodoItem)">X</button>
            </div>
          </li>
      </ul>
    </transition-group>
  </div>
</template>

<script lang>

export default {
  name: 'CreateTodoItem',
  props: ['newtodoItem'],
  data () {
    return {
      info: this.newtodoItem
    }
  },
  methods: {
    printprops: function () {
      console.log(this.newtodoItem.content)
    }
  }
}
</script>

<style>
  *,body{
    overflow:hidden;
  }
  .main-todo{
    overflow-x:hidden;
    width: 100vw;
    display: flex;
    flex:1;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .effectDisplacement-enter-active {
    animation: displacement-effect 3s;
  }
  .effectDisplacement-leave-active {
    animation: displacement-effect 3s reverse;
  }
  @keyframes displacement-effect {
    0% {
      transform: translateX(-5rem);
    }
    25% {
      transform: translateX(-2.5rem);
    }
    50% {
      transform: translateX(0);
    }
    75% {
      transform: translateX(0.5rem);
    }
    100% {
      transform: translateX(0rem);
    }
  }
  .main-item {
    overflow-x:hidden;
    margin-top:0.5rem;
    margin-bottom:0.5rem;
    border-radius: 0.5rem;
    width: 46vw;
    display: flex;
    flex:1;
    flex-direction:row;
    justify-content:flex-start;
  }
  .main-item button{
      margin:0.2rem 0.2rem;
      background: rgb(182, 16, 0);
      color:white;
      border-radius: 2rem;
      width: 2rem;
      height: 2rem;
      border:none;
  }
  .item-todo{
    margin: 0.1rem;
    box-sizing: border-box;
    background: rgb(63, 166, 7);
    width: 40vw;
    height: 25vh;
    border-radius: 20px;
    padding:0.1rem 0.5rem;
    display: grid;
    grid-template-rows: 1fr 2fr 1fr;
  }
  .item-todo div{
    margin: 0.1rem 0;
    border-radius: 0.5rem;
    display: flex;
  }
  .item-todo div:first-child{
    justify-content: center;
    color:white;
  }
  .item-todo div:nth-child(2){
    justify-content: flex-start;
    align-items: start;
    background: #333;
  }
  .item-todo div:nth-child(3){
    justify-content: flex-end;
    align-items: center;
    color:rgb(106, 3, 0);
  }
  .item-todo div span,
  .item-todo div h4{
    margin:0.2rem;
  }
  @media(min-width:320px){
    .main-item {
      width: 92vw;
    }
    .item-todo{
      width: 80vw;
    }
  }
  @media(min-width:768px){
    .main-item {
      width: 66vw;
    }
    .item-todo{
      width: 62vw;
    }
  }
  @media(min-width:1024px){
    .main-item {
      width: 58vw;
    }
    .item-todo{
      width: 54vw;
    }
  }
  @media(min-width:1440px){
    .main-item {
      width: 52vw;
    }
    .item-todo{
      width: 48vw;
    }
  }
  @media(min-width:1530px){
    .main-item {
      width: 52vw;
      max-width: 800px;
    }
    .item-todo{
      width: 50vw;
      max-width: 740px;
    }
  }
</style>
