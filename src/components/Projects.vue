<template>
    <div class="academic">
    	<h2>{{ $t('title')  }}</h2>
			<ul class="projects">
				<li v-for="project in projects" class="project">
					<div class="details">
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
					<h4 v-if="project.links">{{ $t('link') }}: </h4>
					<span v-for="link in project.links">
						<a :href="link.href" target="_blank"><i :class="link.icon"></i> {{ link.name }} </a>
					</span>
					</div>
					<div class="image" v-if="project.img">
						<img :src="project.img" />
					</div>
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
						"title": "CUBS",
						"desc": "In the subject of Website Development, we had to create a webpage for a surf event of our school. This website had to be responsive and built exclusively in HTML5 and CSS3."
					},
					{
						"id": 1,
						"title": "hes.pt",
						"desc": "During this 3 months I developed from scratch their new main website which consisted in a landing page, a product catalog and a back-office with managing capabilities for the landing page content, products for the catalog and user management."
					},
					{ 
						"id": 1,
						"title": "Simple Blackjack",
						"desc": "In the subject of Development of Distributed Applications, a simple blackjack web application was proposed in order to gain experience with asynchronous server-client communications. This application consisted in a server where the game state and game logic was managed, and up to 4 clients who only had access to their own cards."
					},
					{ 
						"id": 3,
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
						"title": "CUBS",
						"desc": "Na unidade curricular de Contrução de Websites, era necessário desenvolver uma página Web para um evento de Surf da escola. Esta página tinha que ser responsive e feita exclusivamente em HTML5 e CSS3."
					},
					{
						"id": 1,
						"title": "hes.pt",
						"desc": "Durantes os 3 meses de estágio, desenvolvi de raíz a página Web principal da empresa, que consistia numa página de entrada, numa página de catálogo de produtos e um back-office com capacidades de gestão dos conteúdos das páginas disponíveis no site e utilizadores."
					},
					{ 
						"id": 2,
						"title": "Simple Blackjack",
						"desc": "Na unidade curricular de Desenvolvimento de Aplicações Distribuídas, foi proposta a criação de um jogo backjack em formato de aplicação web, de forma a conhecer o funcionamento de comunicações assíncronas cliente-servidor. Esta aplicação consiste num servidor onde acontece toda a lógica e estado do jogo, e permite até 4 jogadores, os quais apenas têm acesso às próprias cartas."
					},
					{ 
						"id": 3,
						"title": "MyMusicQoE",
						"desc": "Este projeto consistia na modificação de dois projetos Open Source, Airsonic, um serviço de streaming desenvolvido em Java com capacidades de transcoding ond the fly, e o Ultrasonic, uma aplicação Android capaz de comunicar com servidores Airsonic. O principal objetivo deste projeto era a criação de uma plataforma que capaz de transcodificar uma musica de alta qualidade para uma qualidade aleatória igual ou superior sem o conhecimento do utilizador, e receber avaliações feitas pelos mesmo da qualidade exprimentada da música. Esta aplicação foi lançada no F-Droid (um repositório de aplicações Android FOSS), e foi instalada por centenas de utilizadores. Mais tarde foi conduzido um estudo baseado nas estatísticas recolhidas."
					}
				]
    },
    "ja": {
				"title": "作品",
				"tech": "テクノロジーズ",
				"plat": "プラットフォーム",
				"link": "URL",
				"project_type": [
					{
						"id": 0,
						"name": "学術"
					},
					{
						"id": 1,
						"name": "仕事"
					},
					{
						"id": 2,
						"name": "個人的な"
					}
				],
				"projects": [
					{
						"id": 0,
						"title": "CUBS"
					},
					{
						"id": 1,
						"title": "hes.pt"
					},
					{ 
						"id": 1,
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
						"id": 3,
						"type": 0,
						"smonth": 3,
						"syear": 2018,
						"emonth": 9,
						"eyear": 2018,
						"img": "img/airsonic.png",
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
						"id": 2,
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
					},
					{
						"id": 1,
						"type": 1,
						"smonth": 3,
						"syear": 2015,
						"emonth": 6,
						"eyear": 2015,
						"img": "img/hes.png",
						"platforms": [
							{
								"name": "Web",
								"icon": "fa fa-globe"
							}
						],
						"technologies": [
							{
								"name": "PHP",
								"icon": "devicon-php-plain",
							},
							{
								"name": "Bootstrap",
								"icon": "devicon-bootstrap-plain"
							},
							{
								"name": "Javascript",
								"icon": "devicon-javascript-plain"
							},
							{
								"name": "MySQL",
								"icon": "devicon-mysql-plain"
							}
						]
					},
					{
						"id": 0,
						"type": 0,
						"smonth": 1,
						"syear": 2014,
						"emonth": 3,
						"eyear": 2014,
						"img": "img/cubs.png",
						"platforms": [
							{
								"name": "Web",
								"icon": "fa fa-globe"
							}
						],
						"technologies": [
							{
								"name": "HTML5",
								"icon": "devicon-html5-plain",
							},
							{
								"name": "CSS3",
								"icon": "devicon-css3-plain"
							}
						],
						"links": [
							{
								"href": "https://github.com/RIPASSAS/CUBS",
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

.project {
	position: relative;
	padding: 10px 10px 30px 20px;
	margin: 30px 0;
	background-color: #ccc;
	border-radius: 15px;
  display: -webkit-box;      /* OLD - iOS 6-, Safari 3.1-6 */
  display: -moz-box;         /* OLD - Firefox 19- (buggy but mostly works) */
  display: -ms-flexbox;      /* TWEENER - IE 10 */
  display: -webkit-flex;     /* NEW - Chrome */
  display: flex;             /* NEW, Spec - Opera 12.1, Firefox 20+ */
}

.project:before {
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

.project .details {
	width: 50%;
	display: inline-block;
}

.project .image {
	width: 50%;
	display: inline-block;
}

.project .image img {
	margin-top: 44px;
	width: 100%;
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

/* On screens that are 600px wide or less, make the menu links stack on top of each other instead of next to each other */
@media screen and (max-width: 1024px) {
	.project {
  	display: block;
	}
  .project .details {
		width: 100%;
	}

	.project .image {
		width: 100%;
	}

	.project .image img {
		margin-top: 24px;
		width: 100%;
	}
}

</style>
