<template>
  <div>
    <todo-create-form @add-todo="addTodo"></todo-create-form>
    <ol class="todo-list">
      <todo-item
        v-for="todo in todos"
        :key="todo.id"
        :name="todo.name"
        @item-edited="editTodo(todo.id, $event)"
      />
    </ol>
  </div>
</template>

<script>
import TodoCreateForm from "./TodoCreateForm.vue";
import TodoItem from "./TodoItem.vue";

export default {
  name: "todo-list",
  components: {
    TodoCreateForm,
    TodoItem,
  },
  data() {
    return {
      idNewTodo: 1,
      todos: [{ id: 0, name: "aaa" }],
    };
  },
  methods: {
    addTodo(name) {
      this.todos.push({
        id: this.idNewTodo,
        name,
      });

      this.idNewTodo++;
    },
    editTodo(id, newName) {
      let todo = this.todos.find((todo) => todo.id === id);
      todo.name = newName;
    },
  },
};
</script>
<style scoped>
.todo-list {
  width: 100%;
  padding: 0 1rem;
  flex: 1;
}
</style>
