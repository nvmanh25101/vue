<template>
  <div>
    <form @submit.prevent="submit">
      <input
        class="form__input mb-4"
        type="text"
        placeholder="Todo"
        v-model.trim="newTodo"
      />
      <button class="btn">Add</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "todo-create-form",
  data() {
    return {
      newTodo: "",
    };
  },
  methods: {
    submit() {
      if (!this.newTodo) return;

      this.$emit("add-todo", this.newTodo);
      this.newTodo = "";
    },
  },
};
</script>
