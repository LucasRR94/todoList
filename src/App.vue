<template>
  <div class="main-class">
    <MainLogo v-bind:titleLogo="titlepage"></MainLogo>
    <FormTodoList v-on:loadTodoItem="prepareNewTodoItem"></FormTodoList>
    <CreateTodoItem v-on:delTodoItem="deleteTodoItem" v-bind:newtodoItem="arrTodos"></CreateTodoItem>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import MainLogo from './components/MainLogo.vue'
import FormTodoList from './components/FormTodoList.vue'
import CreateTodoItem from './components/CreateTodoItem.vue'
import TodoItem from './components/lib'
import { v4 as uuidv4 } from 'uuid'

export default Vue.extend({
  name: 'App',
  components: {
    MainLogo,
    FormTodoList,
    CreateTodoItem
  },
  data () {
    return {
      titlepage: 'My To do List',
      arrTodos: new Array<TodoItem>()
    }
  },
  methods: {
    prepareNewTodoItem (cont: string, deadl: Date): void {
      const newTodoItem: TodoItem = { idTodoItem: uuidv4(), content: cont, deadLine: deadl }
      this.arrTodos.push(newTodoItem)
    },
    deleteTodoItem (idTodoItem: string): void{
      this.arrTodos = this.arrTodos.filter((item) => item.idTodoItem !== idTodoItem)
    }
  }
})
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Roboto&display=swap');
*,html,body{
  overflow-y: auto;
  margin: 0 0;
  padding:0 0;
}
.main-class{
  margin:0 0;
  padding:0 0;
  width: 100vw;
  height: 100vh;
}
</style>
