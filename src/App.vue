<template>
  <div id="app">
    <ProductList />
  </div>
</template>

<script>
import ProductList from "./components/ProductsList.vue";

export default {
  components: { ProductList },
  name: "App",
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
