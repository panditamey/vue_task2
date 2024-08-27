<template setup>
  <div id="app">
    <h1 class="bg-primary text-white text-center m-2 p-2">
      {{ name }}'s' Todo List
    </h1>

    <div class="container-fluid p-4">
      <div class="row">
        <div class="col font-weight-bold">Task</div>
        <div class="col-2 font-weight-bold">Done</div>
      </div>
    </div>

    <div class="row" v-for="t in tasks" v-bind:key="t.action">
      <div class="col">{{ t.action }}</div>
      <div class="col">{{ t.done }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      tasks: [
        { action: "Buy Flowers", done: false },
        { action: "Get doctor appoinment", done: false },
        { action: "Collect Tickets", done: true },
        { action: "Attend review meeting", done: false },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
