<template>
  <div id="app">
      <Header />
      <AddTodo v-on:add-todo="addTodo"/>
      <Todos v-bind:todos="todos" 
      v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>

import Header from './components/layout/Header'
import Todos from "./components/Todos"
import AddTodo from './components/AddTodo'

export default {
  name: 'App',
  components: {
    Header,
    Todos,
    AddTodo
  },

  data(){
    return{
      todos: [
        {
          id:1,
          title: "capa",
          completed: false
        },

        {
          id:2,
          title: "telaSemImg",
          completed: true
        },

        {
          id:3,
          title: "telaComImg",
          completed: false
        },
      ]
    }
  },

  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id)
    },

    addTodo(newTodo){
      this.todo = [...this.todos, newTodo]
    }
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body{
  font-family: Nunito, sans-serif;
  line-height: 1.4;
}

.btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }
  .btn:hover {
    background: #666;
  }
</style>
