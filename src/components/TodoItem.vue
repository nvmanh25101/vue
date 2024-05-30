<template>
  <li v-if="!isEditing" class="todo-list__item">
    <span class="todo-list__item-content">{{ name }}</span>
    <div>
      <button @click="isEditing = true" class="btn">Edit</button>
      <button class="btn">Delete</button>
    </div>
  </li>
  <todo-edit-form v-else :name="name" @item-edited="itemEdited" />
</template>

<script>
import TodoEditForm from "./TodoEditForm.vue";

export default {
  name: "todo-item",
  components: {
    TodoEditForm,
  },
  props: {
    name: String,
  },
  data() {
    return {
      isEditing: false,
    };
  },
  methods: {
    itemEdited(newName) {
      this.$emit("item-edited", newName);
      this.isEditing = false;
    },
  },
};
</script>
<style scoped>
.todo-list__item {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0.5em;
  margin-bottom: 0.5em;
  border-radius: 3px;
}

.todo-list__item-content {
  color: var(--color-main);
  margin-right: 1em;
}
</style>
