<template>
  <div id="app">
    <h3 class="bg-primary text-white text-center m-2 p-2">
      {{ name }}'s Todo List
    </h3>
    <div class="container-fluid" p-4>
      <div class="row">
        <div class="col font-weight-bold">Task</div>
        <div class="col-2 font-weight-bold">Done</div>
      </div>

      <div class="row" v-for="t in filteredTasks" v-bind:key="t.action">
        <div class="col">{{ t.action }}</div>
        <div class="col-2 text-center">
          <input type="checkbox" v-model="t.done" class="form-check-input" />
        </div>
        <button class="btn btn-primary" v-on:click="deleteItem(t)">
          Delete
        </button>
      </div>

      <!-- Input box -->
      <div class="row py-2">
        <div class="col">
          <input v-model="newItemText" class="form-control" />
        </div>
        <div class="col-2">
          <button class="btn btn-primary" v-on:click="addNewItem">Add</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Todo",
  data() {
    return {
      name: "Amey",
      tasks: [
        { action: "Buy milk", done: true },
        { action: "Clean bathroom", done: false },
        { action: "Feed dog", done: false },
        { action: "Learn Vue", done: true },
      ],
      hideCompleted: true,
      newItemText: "",
    };
  },
  computed: {
    filteredTasks() {
      return this.hideCompleted
        ? this.tasks.filter((t) => !t.done)
        : this.tasks;
    },
  },
  methods: {
    addNewItem() {
      this.tasks.push({ action: this.newItemText, done: false });
      this.newItemText = "";
    },
    deleteItem(task) {
      this.tasks.splice(this.tasks.indexOf(task), 1);
    },
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
