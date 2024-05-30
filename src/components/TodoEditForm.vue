<template>
  <div>
    <form @submit.prevent="submit">
      <input
        class="form__input"
        type="text"
        placeholder="Todo"
        v-model.trim="newName"
      />
      <button class="btn">Save</button>
      <button type="button" class="btn">Cancel</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "todo-edit-form",
  props: {
    name: String,
  },
  data() {
    return {
      newName: "",
    };
  },
  methods: {
    submit() {
      if (this.newName && this.newName !== this.name) {
        this.$emit("item-edited", this.newName);
      }
    },
  },
  mounted() {
    this.newName = this.name;
  },
};
</script>
