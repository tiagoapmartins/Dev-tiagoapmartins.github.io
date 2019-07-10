<template>
  <div id="app">
    <SideBar v-on:locale-select="changeLocale" v-on:page-select="changePage" />
		<div id="content">
			<keep-alive>
				<component v-bind:is="selectedComponent"></component>
			</keep-alive>
		</div>
	</div>
</template>

<script>
import Academic from "./components/Academic.vue";
import Projects from "./components/Projects.vue";
import SideBar from "./components/SideBar.vue";

export default {
  name: "app",
  components: {
    Academic,
		Projects,
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
  /* height: 100%; /* needed for container min-height */
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
/* On screens that are 600px wide or less, make the menu links stack on top of each other instead of next to each other */
@media screen and (max-width: 600px) {
	html,
	body{
		/*height: auto;*/
	}
	#content {
		margin-left: 0;
	}
	#content>div{
		padding: 0 15px 0 15px;
	}
	#content>div>h2{
		margin: 0;
		padding-top: 0;
	}
}
</style>
