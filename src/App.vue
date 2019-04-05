<template>
  <div id="app">
    <SideBar v-on:locale-select="changeLocale" />
		<div id="content">
			<Academic />
		</div>
	</div>
</template>

<script>
import Academic from "./components/Academic.vue";
import SideBar from "./components/SideBar.vue";

export default {
  name: "app",
  components: {
    Academic,
    SideBar
  },
	methods: {
		changeLocale(loc){
			this.$i18n.locale=loc;
		}	
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
#content {
	margin-left: 350px;
}
</style>
