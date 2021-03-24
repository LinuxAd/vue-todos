<template>
  <div id="app">
    <Todo title="Today"></Todo>
  </div>
</template>

<script>
import TodoList from '@/components/todo-list.vue'
export default {
  components: {
    'Todo': TodoList,
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
