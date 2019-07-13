<template>
  <div id="app">
    <Header v-bind:title="title" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
    <AddTodo v-on:add-todo="addTodo" />
  </div>
</template>

<script>
import Header from './components/layout/Header'

import Todos from './components/Todos'
import AddTodo from './components/AddTodo'

export default {
  name: 'app',
  components: {
    Header,
    Todos,
    AddTodo
  },
  data() {
    return {
      title: "Max's Todo List",
      todos: [
        {
          id: 1,
          title: "Do the dishes",
          completed: false
        },
        {
          id: 2,
          title: "Learn Vue.js",
          completed: false
        },
        {
          id: 3,
          title: "Go see the Bonneville fish hatchery",
          completed: true
        },
        {
          id: 4,
          title: "Apply for more jobs",
          completed: false
        },
        {
          id: 5,
          title: "Apply to Graduate Schools",
          completed: false
        }
      ]
    }
  },
  methods: {
    addTodo(newTodo) {
      this.todos.push(newTodo)
    },

    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id != id)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  margin: auto;
  max-width: 800px;
}
</style>
