<template>
    <div class="academic">
    	<h2>{{ $t('title')  }}</h2>
			<ul class="projects">
				<li v-for="project in projects">
					<span>{{ project.smonth }}<span v-if="$i18n.locale=='ja'">月</span><span v-else>/</span>{{ project.syear }}<span v-if="$i18n.locale=='ja'">年</span> - {{ project.emonth }}<span v-if="$i18n.locale=='ja'">月</span><span v-else>/</span>{{ project.eyear }}<span v-if="$i18n.locale=='ja'">年</span></span>
					<h3><b>{{ $t(i18n_array('projects',project.id)+'.title')  }}</b><br/> {{ $t(i18n_array('project_type',project.type)+'.name')  }}</h3>
					<p>
						{{ $t(i18n_array('projects',project.id)+'.desc')  }}
					</p>
					<h4>{{ $t('plat') }}: </h4>
					<span class="pill" v-for="platform in project.platforms">
						<i :class="platform.icon"></i> {{ platform.name }}
					</span>
					<br />
					<h4>{{ $t('tech') }}: </h4>
					<span  class="pill" v-for="tech in project.technologies">
						<i :class="tech.icon"></i> {{ tech.name }}
					</span>
					<br />
					<h4>{{ $t('link') }}: </h4>
					<span v-for="link in project.links">
						<a :href="link.href" target="_blank"><i :class="link.icon"></i> {{ link.name }} </a>
					</span>
				</li>
			</ul>
    </div>
</template>

<i18n>
{
    "en": {
       	"title": "Projects",
				"tech": "Technologies",
				"plat": "Platforms",
				"link": "Links",
				"project_type": [
					{
						"id": 0,
						"name": "School"
					},
					{
						"id": 1,
						"name": "Work"
					},
					{
						"id": 2,
						"name": "Personal"
					}
				],
				"projects": [
					{ 
						"id": 0,
						"title": "Simple Blackjack",
						"desc": "In the subject of Development of Distributed Applications, a simple blackjack web application was proposed in order to gain experience with asynchronous server-client communications. This application consisted in a server where the game state and game logic was managed, and up to 4 clients who only had access to their own cards."
					},
					{ 
						"id": 1,
						"title": "MyMusicQoE",
						"desc": "This project consisted in modifying a couple of open source projects, Airsonic, a streaming service written in Java with on the fly file transcoding capability, and Ultrasonic, an Android application that is capable of communicating with an Airsonic server. The main objective of this project was to create a platform able to randomly transcode an high quality music file to the same or lower quality without the user’s knowledge, and receive rating based on the perceived audio quality from the user. This project was deployed on F-Droid (a popular FOSS Android repository), and was installed by hundreds of users. Later, a study was made based on the gathered statistics."
					}
				]
		},
    "pt": {
        "title": "Projetos",
				"tech": "Tecnologias",
				"plat": "Plataformas",
				"link": "Links",
				"project_type": [
					{
						"id": 0,
						"name": "Académico"
					},
					{
						"id": 1,
						"name": "Trabalho"
					},
					{
						"id": 2,
						"name": "Pessoal"
					}
				],
				"projects": [
					{ 
						"id": 0,
						"title": "Simple Blackjack",
						"desc": "Na unidade curricular de Desenvolvimento de Aplicações Distribuídas, foi proposta a criação de um jogo backjack em formato de aplicação web, de forma a conhecer o funcionamento de comunicações assíncronas cliente-servidor. Esta aplicação consiste num servidor onde acontece toda a lógica e estado do jogo, e permite até 4 jogadores, os quais apenas têm acesso às próprias cartas."
					}
				]
    },
    "ja": {
				"title": "家",
				"tech": "テクノロジーズ",
				"plat": "プラットフォーム",
				"link": "URL",
				"project_type": [
					{
						"id": 0,
						"name": "学術 (Maybe wrong)"
					},
					{
						"id": 1,
						"name": "作業 (Maybe wrong)"
					},
					{
						"id": 2,
						"name": "個人的な (Maybe wrong)"
					}
				],
				"projects": [
					{ 
						"id": 0,
						"title": "シンプルブラックジャック"
					}
				]
    }
}
</i18n>

<script>
export default {
  name: "Projects",
  props: {
    
  },
  data () {
      return {
				projects: [
					{
						"id": 1,
						"type": 0,
						"smonth": 3,
						"syear": 2018,
						"emonth": 9,
						"eyear": 2018,
						"platforms": [
							{
								"name": "Web",
								"icon": "fa fa-globe"
							},
							{
								"name": "Android",
								"icon": "fab fa-android"
							}
						],
						"technologies": [
							{
								"name": "Java",
								"icon": "devicon-java-plain",
							},
							{
								"name": "Java Servlet Pages",
								"icon": "devicon-java-plain"
							},
							{
								"name": "Android SDK",
								"icon": "devicon-android-plain"
							},
							{
								"name": "Tomcat",
								"icon": "devicon-tomcat-line"
							}
						],
						"links": [
							{
								"href": "https://github.com/RIPASSAS/airsonic",
								"name": "Github",
								"icon": "devicon-github-plain"
							}
						]
					},
					{
						"id": 0,
						"type": 0,
						"smonth": 12,
						"syear": 2017,
						"emonth": 2,
						"eyear": 2018,
						"platforms": [
							{
								"name": "Web",
								"icon": "fa fa-globe"
							}
						],
						"technologies": [
							{
								"name": "Node.js",
								"icon": "devicon-nodejs-plain",
							},
							{
								"name": "Vue.js",
								"icon": "devicon-vuejs-plain"
							},
							{
								"name": "Laravel",
								"icon": "devicon-laravel-plain"
							},
							{
								"name": "Vagrant",
								"icon": "devicon-vagrant-plain"
							},
							{
								"name": "Bootstrap",
								"icon": "devicon-bootstrap-plain"
							}
						],
						"links": [
							{
								"href": "https://github.com/rockandre/DAD_BlackJack_Server",
								"name": "Github",
								"icon": "devicon-github-plain"
							},
							{
								"href": "https://github.com/rockandre/DAD_BlackJack_Client",
								"name": "Github",
								"icon": "devicon-github-plain"
							}
						]
					}		
				]
      }
  },
	methods: {
		i18n_array (arr,index) {
			return arr+'['+index+']';
		}
	}
};
</script>

<style scoped lang="scss">
.academic {
	padding-top: 0px;
	padding-left: 30px;
	text-align: left;
}

.projects li h3 {
	font-weight: normal;
}

.projects li h4 {
	margin: 18px 0 5px 0;
	font-weight: normal;
}

img {
  border-radius: 50%;
  max-width: 300px;
}

ul {
  list-style-type: none;
  padding: 10px;
}

ul.projects {
	position: relative;
}

ul.projects:before {
	position: absolute;
	content: '';
	display: inline-block;
	height: 100%;
	border: 1px dashed #777;
	z-index: 1;
}

.projects li {
	position: relative;
	padding: 10px 10px 30px 20px;
	margin: 30px 0;
	background-color: #ccc;
	border-radius: 15px;
}

.projects li:before {
	position: absolute;
	left: -8px;
	top: 10px;
	content: '';
	display: inline-block;
	border: 2px solid #777;
	background-color: #2c3e50;
	width: 15px;
	height: 15px;
	border-radius: 10px;
	z-index: 1;
}

a {
  color: #31a872;
  text-decoration: none;
}

.pill {
	display: inline-block;
	padding: 3px;
	background-color: #aaa;
	margin: 2px;
	border-radius: 5px;
}
</style>
