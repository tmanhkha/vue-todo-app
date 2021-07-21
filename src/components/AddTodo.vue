<template>
  <div>
    <form @submit="addTodo">
      <input name="title" type="text" v-model="title"/>
      <button type="submit">Add</button>
    </form>
  </div>
</template>

<script>
import { v4 } from "uuid";

export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addTodo(e) {
      e.preventDefault();

      const newTodoObj = {
        id: v4(),
        title: this.title,
        completed: false
      }

      this.$emit('add-todo', newTodoObj)
      this.title = ''
    }
  }
}
</script>

<style scoped>
</style>
