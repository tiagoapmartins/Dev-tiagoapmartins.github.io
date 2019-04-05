<template>
    <div class="academic">
    	<h2>{{ $t('title')  }}</h2>
			<ul class="degrees">
				<li v-for="degree in $t('degrees')">
					<span>{{ degree.sdate }} - {{ degree.edate }}</span>
					<h3><b>{{ degree.title  }}</b><br/> {{ degree.course  }}</h3>
					<span>{{ degree.school  }}</span>
				</li>
			</ul>
    </div>
</template>

<i18n>
{
    "en": {
       	"title": "Academic Background",
				"degrees": [
					{ 
						"title": "Master's Degree",
						"course": "Cybersecurity and Digital Forensics",
						"school": "Polytechnic Institute of Leiria (IPLeiria)",
						"sdate": "2018",
						"edate": "2020"
					},
					{ 
						"title": "Bachelor's Degree",
						"course": "Computer Engineering",
						"school": "Polytechnic Institute of Leiria (IPLeiria)",
						"sdate": "2015",
						"edate": "2018"
					},
					{
						"title": "Technological Specialization Course",
						"course": "Building and Administrating Websites",
						"school": "Polytechnic Institute of Leiria (IPLeiria)",
						"sdate": "2013",
						"edate": "2015"
					}
				]
		},
    "pt": {
        "title": "Percurso Académico",
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
				"title": "学歴",
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
  name: "Academic",
  props: {
    
  },
  data () {
      return {
      }
  },
	methods: {
	}
};
</script>

<style scoped lang="scss">
.academic {
	padding-top: 10px;
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
.degrees li {
	position: relative;
	padding: 0 10px 30px 20px;
	border-left: solid 2px #777;
}

.degrees li:before {
	position: absolute;
	left: -10px;
	top: 0px;
	content: '';
	display: inline-block;
	border: 2px solid #777;
	background-color: #2c3e50;
	width: 15px;
	height: 15px;
	border-radius: 10px;
}

a {
  color: #42b983;
  text-decoration: none;
}
</style>
