<template>
  <div>
    <div v-if="isEdit">
      {{ todo.body }}
      <div class="btn-group">
        <button
          type="button"
          class="btn btn-default btn-sm"
          @click="changeIsEdit">
          Edit
        </button>
        <button
          type="button"
          class="btn btn-default btn-sm"
          @click="complete(todo)">
          Complete
        </button>
        <button
          type="button"
          class="btn btn-default btn-sm"
          @click="remove(todo)">
          Remove
        </button>
      </div>
    </div>
    <div v-else>
      <input
        :value="todo.body"
        class="form-control"
        @keyup="updatedTodo = $event.target.value"
      >
      <button
        type="button"
        class="btn btn-primary"
        @click="edit(todo, updatedTodo)">Edit</button>
    </div>
  </div>
</template>

<script>
export default{
  props: ['todo'],
  data: function () {
    return {
      isEdit: true,
      updatedTodo: ''
    }
  },
  methods: {
    changeIsEdit () {
      this.isEdit = !this.isEdit
    },
    edit (todo, updatedTodo) {
      this.changeIsEdit()
      this.$store.dispatch('editTodo', {todo, updatedTodo})
    },
    complete (todo) {
      this.$store.dispatch('completeTodo', todo)
    },
    remove (todo) {
      this.$store.dispatch('removeTodo', todo)
    }
  }
}
</script>
<style lang="stylus">
  .btn-group
    float: right;
</style>
