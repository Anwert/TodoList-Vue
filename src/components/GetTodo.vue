<template>
  <div
    id="get-todo"
    class="container">
    <input
      :value="newTodo"
      class="form-control"
      placeholder="I need to..."
      @change="getTodo">
    <button
      class="btn btn-primary"
      @click="addTodo">Add Todo</button>
  </div>
</template>
<script>
export default{
  computed: {
    newTodo () {
      return this.$store.getters.newTodo
    }
  },
  methods: {
    getTodo (e) {
      this.$store.dispatch('getTodo', e.target.value)
    },
    addTodo () {
      this.$store.dispatch('addTodo')
      this.$store.dispatch('clearTodo')
    }
  }
}
</script>
