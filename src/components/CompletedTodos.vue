<template>
  <div
    id="completed-todos"
    class="container">
    <h3 v-if="completed.length > 0">Completed({{ completed.length }})</h3>
    <ul class="list-group">
      <li
        v-for="todo in completed"
        class="list-group-item">
        {{ todo.body }}
        <button
          type="button"
          class="btn btn-default btn-sm"
          @click="remove(todo)">
          <span class="glyphicon glyphicon-remove-circle"/> Remove
        </button>
      </li>
    </ul>
  </div>
</template>
<script>
export default{
  computed: {
    completed () {
      return this.$store.getters.completedTodos
    }
  },
  methods: {
    remove (todo) {
      this.$store.dispatch('removeTodo', todo)
    }
  }
}
</script>
