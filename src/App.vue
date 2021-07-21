<template>
  <div id="app">
    <h2>Todo list</h2>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos :todos="todos" v-on:delete-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from './components/Todos'
import AddTodo from './components/AddTodo'

export default {
  name: 'App',
  components: {
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: []
    }
  },
  methods: {
    addTodo(newTodoObj) {

      this.todos = [...this.todos, newTodoObj]
    },
    deleteTodo(id) {
      this.todos = this.todos.filter(item => item.id != id)
    }
  }
}
</script>

<style>
</style>
