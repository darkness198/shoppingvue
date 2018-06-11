<template>
  <div id="app">
    
    
    <ShoppingListContainer :itemsArr="itemsArr" ></ShoppingListContainer>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import ShoppingListContainer from "./components/ShoppingListContainer.vue";

export default {
  name: "app",
  data() {
    return {
      itemsArr: []
    }
  },
  components: {
    HelloWorld,
    ShoppingListContainer
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
