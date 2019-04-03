<template>
  <div id="app">
    <SideBar lang="jp" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import SideBar from "./components/SideBar.vue";

export default {
  name: "app",
  components: {
    HelloWorld,
    SideBar
  }
};
</script>

<style lang="scss">
html,
body {
    margin: 0;
    padding: 0;
    height: 100%; /* needed for container min-height */
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
}
</style>
