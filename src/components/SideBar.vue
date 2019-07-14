<template>
    <div class="sideBar">
        <ul class="langSelect">
            <li>
                <a @click="$emit('locale-select','en')" href="#">English</a>
            </li>
            <li>
                <a @click="$emit('locale-select','pt')" href="#">Português</a>
            </li>
            <li>
                <a @click="$emit('locale-select','ja')" href="#">日本語</a>
            </li>
        </ul>
        <div class="self-img">
            <img src="../assets/me.jpg">
        </div>
        <div>
					<h2 class="name">Tiago Martins</h2>
            <h4 v-if="$i18n.locale=='ja'" class="pronunciation">ティアゴマルチンス</h4>
            <p class="shortBio">
                {{ $t('bio') }}
            </p>
        </div>
        <div>
            <nav>
                <ul>
									<li v-for="link in links">
												<a @click="$emit('page-select',link.page)" href="#content">{{ $t(i18n_array('links',link.id)+'.name') }}</a>
                    </li>
                </ul>
            </nav>
        </div>
    </div>
</template>

<i18n>
{
    "en": {
		"bio": "I'm a software and full-stack web developer that focuses on security",
				"links": [
					{
						"id": 0,
						"name" : "Projects"
					},
					{ 
						"id": 1,
						"name" : "Academic Background"
					},
					{
						"id": 2,
						"name" : "Contacts"
					}
				]
		},
    "pt": {
        "bio": "Sou um desenvolvedor de software e web que tem um foco na segurança",
				"links": [
					{
						"id": 0,
						"name" : "Projetos"
					},
					{
						"id": 1,
						"name" : "Percurso Académico"
					},
					{
						"id": 2,
						"name" : "Contactos"	
					}
				]
    },
    "ja": {
        "bio": "私はソフトウェア開発とWebエンジニアです。セキュリティは私の一番の配慮。",
				"links": [
					{
						"id": 0,
						"name" : "作品"
					},
					{
						"id": 1,
						"name" : "学歴"
					},

					{
						"id": 2,
						"name" : "連絡先"
					}
				]
    }
}
</i18n>

<script>
export default {
  name: "SideBar",
  props: {
    
  },
  data () {
      return {
    		birth:  new Date('1995-05-28'),
				links: [
					{
						"id": 0,
						"page": "Projects"
					},
					{
						"id": 1,
						"page": "Academic"
					},
					{
						"id": 2,
						"page": "Contacts"
					}
				]
      }
  },
	methods: {
		i18n_array (arr,index) {
			return arr+'['+index+']';
		}
	},
	computed: {
		age: function (){
			return Math.floor((Date.now() - this.birth) / (1000 * 60 * 60 * 24 * 365.5))
		}
	}
};
</script>

<style scoped lang="scss">
.sideBar {
  position: fixed;
	left: 0;
	top: 0;
  height: 100%;
	width: 350px;
  color: #fff;
  background: #2c3e50;
  background-image: url("../assets/Japanese_Wave_Pattern.svg");
  background-size: 950px;
}

.shortBio {
	margin: 18px 5px;
}

/* On screens that are 600px wide or less, make the menu links stack on top of each other instead of next to each other */
@media screen and (max-width: 600px) {
  .sideBar {
		position: relative;
    width: 100%;
		margin-bottom: 20px;
  }
	.langSelect{
		margin: 0;
		padding: 18px 0 18px 0;
	}
	.self-img img {
  	max-width: 200px !important;
	}
}


.self-img img {
  border-radius: 50%;
  max-width: 300px;
}

.name {
	margin-bottom: 0;
}

.pronunciation {
	margin-top: 5px;
}

ul {
  list-style-type: none;
  padding: 0;
}

.langSelect li {
  display: inline-block;
  margin: 0 10px;
}

nav li {
  padding: 10px;
  font-weight: bold;
}

a {
  color: #42b983;
  text-decoration: none;
}
</style>
