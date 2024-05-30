<template>
  <div class="flex justify-center items-center flex-col">
    <img
      src="https://vuejs.org/images/logo.png"
      width="100"
      alt="vue"
      class="logo block mb-4"
    />
    <todo-list />
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";

export default {
  name: "app",
  components: {
    TodoList,
  },
};
</script>

<!-- CSS libraries -->
<style>
body {
  --color-main: #4fc08d;
}

button {
  background: none;
  border: none;
}

.btn {
  font-size: 14px;
  margin: 0 0.5em;
  border-radius: 2em;
  padding: 0.75em 1.5em;
  cursor: pointer;
  background: none;
  color: darken(var(--color-main), 20%);
  border: 1px solid;
  letter-spacing: 1px;
  color: var(--color-main);
  border: var(--color-main) 1px solid;
  transition: 250ms ease-out;
}

.form__input {
  font-size: 14px;
  margin: 0 0.5em;
  border-radius: 2em;
  padding: 0.75em 1.5em;
  background: none;
  border: #e3e3e3 1px solid;
  transition: border 250ms ease-out;
}

.form__input:focus {
  border: var(--color-main) 1px solid;
  outline: none;
}
</style>
