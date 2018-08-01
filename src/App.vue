<template>
  <div>
    <CompletedTodos/>
    <GetTodo/>
    <CurrentTodos/>
  </div>
</template>

<script>
import GetTodo from './components/GetTodo.vue'
import CurrentTodos from './components/CurrentTodos.vue'
import CompletedTodos from './components/CompletedTodos.vue'

export default {
  components: {
    GetTodo,
    CurrentTodos,
    CompletedTodos
  }
}
</script>

<style lang="stylus">
  @import "../assets/app.styl"
</style>
