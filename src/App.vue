<template>
  <div id="app">
    <SideBar v-on:locale-select="changeLocale" v-on:page-select="changePage" />
		<div id="content">
			<component v-bind:is="selectedComponent"></component>
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
	data () {
		return {
			selectedComponent: "Academic"
		}
	},
	methods: {
		changeLocale(loc){
			this.$i18n.locale=loc;
		},
		changePage(page){
			console.log(page);	
			this.selectedComponent=page;
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
	background-color: #e7e7e1;
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
