<template>
    <div class="academic">
    	<h2>{{ $t('title')  }}</h2>
			<ul class="degrees">
				<!--<li v-for="degree in $t('degrees')">-->
				<li v-for="degree in degrees">
					<span>{{ degree.sdate }}<span v-if="$i18n.locale=='ja'">年</span> - {{ degree.edate }}<span v-if="$i18n.locale=='ja'">年</span></span>
					<h3><b>{{ $t(i18n_array('degrees',degree.id)+'.title')  }}</b><br/> {{ $t(i18n_array('degrees',degree.id)+'.course')  }}</h3>
					<span>{{ $t(i18n_array('degrees',degree.id)+'.school')  }} ({{ degree.school_short  }}) </span>
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
						"id": 0,
						"title": "Master's Degree",
						"course": "Cybersecurity and Digital Forensics",
						"school": "Polytechnic Institute of Leiria"
					},
					{
						"id": 1,
						"title": "Bachelor's Degree",
						"course": "Computer Science",
						"school": "Polytechnic Institute of Leiria"
					},
					{
						"id": 2,
						"title": "Technological Specialization Course",
						"course": "Building and Administrating Websites",
						"school": "Polytechnic Institute of Leiria"
					}
				]
		},
    "pt": {
        "title": "Percurso Académico",
				"degrees": [
					{ 
						"id": 0,
						"title": "Mestrado",
						"course": "Cibersegurança e Informática Forense",
						"school": "Instituto Politécnico de Leiria"
					},
					{ 
						"id": 1,
						"title": "Licenciatura",
						"course": "Engenharia Informática",
						"school": "Instituto Politécnico de Leiria",
						"sdate": "2015",
						"edate": "2018"
					},
					{ 
						"id": 2,
						"title": "Curso de Especialização Tecnológica",
						"course": "Construção e Administração de Websites",
						"school": "Instituto Politécnico de Leiria"
					}
				]
    },
    "ja": {
				"title": "学歴",
				"degrees": [
					{ 
						"id": 0,
						"title": "修士号",
						"course": "サイバーセキュリティとデジタルフォレンジック",
						"school": "レイリア工科大学"
					},
					{ 
						"id": 1,
						"title": "学士号",
						"course": "計算機科学",
						"school": "レイリア工科大学"
					},
					{ 
						"id": 2,
						"title": "技術専門コース",
						"course": "Webサイト構築と管理",
						"school": "レイリア工科大学"
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
			degrees: [
				{ 
						"id": 0,
						"sdate": "2018",
						"edate": "2020",
						"school_short": "IPLeiria"
					},
					{ 
						"id": 1,
						"sdate": "2015",
						"edate": "2018",
						"school_short": "IPLeiria"
					},
					{ 
						"id": 2,
						"sdate": "2013",
						"edate": "2015",
						"school_short": "IPLeiria"
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
