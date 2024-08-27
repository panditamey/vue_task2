<template>
  <div id="app">
    <h3 class="bg-primary text-white text-center m-2 p-2">Todo List</h3>

    <Todo />
  </div>
</template>

<script>
import Todo from "./components/TodoList.vue";

export default {
  name: "App",
  components: {
    Todo,
  },
};
</script>
