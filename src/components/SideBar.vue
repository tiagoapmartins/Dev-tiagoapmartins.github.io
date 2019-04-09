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
        <div>
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
												<a @click="$emit('page-select',link.page)" href="#">{{ $t(i18n_array('links',link.id)+'.name') }}</a>
                    </li>
                </ul>
            </nav>
        </div>
    </div>
</template>

<i18n>
{
    "en": {
        "bio": "Default english biography",
				"links": [
					{ 
						"id": 0,
						"name" : "Academic Background"
					},
					{
						"id": 1,
						"name" : "Projects"
					},
					{
						"id": 2,
						"name" : "Contacts"
					}
				]
		},
    "pt": {
        "bio": "Biografia em português",
				"links": [
					{
						"id": 0,
						"name" : "Percurso Académico"
					},
					{
						"id": 1,
						"name" : "Projetos"
					},
					{
						"id": 2,
						"name" : "Contactos"	
					}
				]
    },
    "ja": {
        "bio": "日本語のビオグラフィ",
				"links": [
					{
						"id": 0,
						"name" : "学歴"
					},
					{
						"id": 1,
						"name" : "家"
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
						"page": "Academic"
					},
					{
						"id": 1,
						"page": "Projects"
					},
					{
						"id": 2,
						"page": ""
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
  position: absolute;
	left: 0;
	top: 0;
  height: 100%;
	min-width: 350px;
  color: #fff;
  background: #2c3e50;
  background-image: url("../assets/Japanese_Wave_Pattern.svg");
  background-size: 950px;
}

img {
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
