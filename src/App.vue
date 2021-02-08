<template>
  <div id="app">
      <Header />
      <AddTodo v-on:addTodo= "addTodo"/>
      <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
      <TodoItem v-bind:todo="todo"/>
  
  </div>
</template>

<script>
import Header from './components/Layout/Header.vue'
import Todos from './components/Todos.vue';
import AddTodo from './components/AddTodo.vue'
import TodoItem from './components/TodoItem.vue'
export default {
  name: 'App',
  components: {
    Header,
    Todos,
    AddTodo,
    TodoItem
  }, 
  data: function(){
     return{
       todos: [],
     }
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo){
      this.todos= [...this.todo, newTodo]
    }
  },
  created(){

  },


}
</script>

<style>
  *{
   box-sizing: border-box;
   margin: 0;
   padding: 0;
  }
  body{
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }

  .btn{
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }
  .btn:hover{
    background: #666;
  }
</style>
