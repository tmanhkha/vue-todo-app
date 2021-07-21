<template>
  <div :class="{ completed: todo.completed }">
    <p>{{ todo.title }}</p>
    <button @click="markComplete">{{ todo.completed ? 'In Complete' : 'Complete' }}</button>
    <button @click="$emit('delete-todo', todo.id)">Delete</button>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  props: [
    "todo"
  ],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed
    }
  }
}
</script>

<style scoped>
  .completed {
    text-decoration: line-through;
  }
</style>
