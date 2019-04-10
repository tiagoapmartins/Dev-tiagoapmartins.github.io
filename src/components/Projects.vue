<template>
    <div class="academic">
    	<h2>{{ $t('title')  }}</h2>
			<ul class="projects">
				<li v-for="project in projects">
					<h3><b>{{ $t(i18n_array('projects',project.id)+'.title')  }}</b><br/> {{ $t(i18n_array('project_type',project.type)+'.name')  }}</h3>
					<span v-for="platform_id in project.platforms">
						{{ platforms[platform_id].name }}
					</span>
					<br />
					<span v-for="framework_id in project.frameworks">
						{{ frameworks[framework_id].name }}
					</span>
					<br />
					<span v-for="progLang_id in project.progLangs">
						{{ progLangs[progLang_id].short }}
					</span>
				</li>
			</ul>
    </div>
</template>

<i18n>
{
    "en": {
       	"title": "Projects",
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
						"title": "Simple Blackjack"
					}
				]
		},
    "pt": {
        "title": "Projetos",
				"degrees": [
					{ 
						"title": "Mestrado",
						"course": "Cibersegurança e Informática Forense",
						"school": "Instituto Politécnico de Leiria (IPLeiria)",
						"sdate": "2018",
						"edate": "2020"
					},
					{ 
						"title": "Licenciatura",
						"course": "Engenharia Informática",
						"school": "Instituto Politécnico de Leiria (IPLeiria)",
						"sdate": "2015",
						"edate": "2018"
					},
					{ 
						"title": "Curso de Especialização Tecnológica",
						"course": "Construção e Administração de Websites",
						"school": "Instituto Politécnico de Leiria (IPLeiria)",
						"sdate": "2013",
						"edate": "2015"
					}
				]
    },
    "ja": {
				"title": "家",
				"degrees": [
					{ 
						"title": "修士号",
						"course": "サイバーセキュリティとデジタルフォレンジック",
						"school": "レイリア工科大学 (IPLeiria)",
						"sdate": "2018年",
						"edate": "2020年"
					},
					{ 
						"title": "学士号",
						"course": "情報工学",
						"school": "レイリア工科大学 (IPLeiria)",
						"sdate": "2015年",
						"edate": "2018年"
					},
					{ 
						"title": "技術専門コース",
						"course": "Webサイト構築と管理",
						"school": "レイリア工科大学 (IPLeiria)",
						"sdate": "2013年",
						"edate": "2015年"
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
				progLangs: [
					{
						"id": 0,
						"name": "HyperText Markup Language",
						"short": "HTML"
					},
					{
						"id": 1,
						"name": "Cascade Style Sheet",
						"short": "CSS"
					},
					{
						"id": 2,
						"name": "Javascript",
						"short": "JS"
					},
					{
						"id": 3,
						"name": "eXtended Markup Language",
						"short": "XML"
					},
					{
						"id": 4,
						"name": "PreProcesse Hyperext",
						"short": "PHP"
					},
					{
						"id": 5,
						"name": "C"
					},
					{
						"id": 6,
						"name": "Java",
						"types": [
							{
								"id": 0,
								"name": "Standard Edition",
								"short": "SE"
							},
							{
								"id": 1,
								"name": "Enterprise Edition",
								"short": "EE"
							}
						]
					},
					{
						"id": 7,
						"name": "Structured Query Language",
						"short": "SQL"
					}
				],
				frameworks: [
					{
						"id": 0,
						"id_pl": [0,1,2],
						"name": "Twitter Bootstrap"
					},
					{
						"id": 1,
						"id_pl": [2],
						"name": "Node.js"
					},
					{
						"id": 2,
						"id_pl": [2],
						"name": "Vue.js"
					},
					{
						"id": 3,
						"id_pl": [4],
						"name": "Laravel"
					}
				],
				platforms: [
					{
						"id": 0,
						"name": "Web",
					},
					{
						"id": 1,
						"name": "Windows",
					},
					{
						"id": 2,
						"name": "Linux",
					},
					{
						"id": 3,
						"name": "Android",
					}
				],
				projects: [
					{
						"id": 0,
						"type": 0,
						"platforms": [0],
						"progLangs": [0,1,2,4,7],
						"frameworks": [0,1,2,3]
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

.degrees li h3 {
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

ul.degrees {
	position: relative;
}

ul.degrees:before {
	position: absolute;
	content: '';
	display: inline-block;
	height: 100%;
	border: 1px dashed #777;
	z-index: 1;
}

.degrees li {
	position: relative;
	padding: 10px 10px 30px 20px;
	margin: 30px 0;
	background-color: #ccc;
	border-radius: 15px 0 15px 0;
}

.degrees li:before {
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
  color: #42b983;
  text-decoration: none;
}
</style>
