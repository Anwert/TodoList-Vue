<template>
  <div
    id="current-todos"
    class="container">
    <h3 v-if="todos.length > 0">Current({{ todos.length }})</h3>
    <ul class="list-group">
      <li
        v-for="todo in todos"
        class="list-group-item">
        <Todo :todo="todo"/>
      </li>
    </ul>
  </div>
</template>

<script>
import Todo from './Todo.vue'

export default{
  components: {
    Todo
  },
  computed: {
    todos () {
      return this.$store.getters.todos
    }
  }
}
</script>
<style lang="stylus">
  .btn-group
    float: right;
</style>
