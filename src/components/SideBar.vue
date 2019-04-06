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
									<li v-for="link in $t('links')">
												<a @click="$emit('page-select',link.page)" href="#">{{ link.name }}</a>
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
					{ "name" : "Academic Background", "page" : "Academic" },
					{ "name" : "Projects", "page" : "" },
					{ "name" : "Contacts", "page" : "" }
				]
		},
    "pt": {
        "bio": "Biografia em português",
				"links": [
					{ "name" : "Percurso Académico", "page" : "Academic" },
					{ "name" : "Projetos", "page" : "" },
					{ "name" : "Contactos", "page" : "" }
				]
    },
    "ja": {
        "bio": "日本語のビオグラフィ",
				"links": [
					{ "name" : "学歴", "page" : "Academic" },
					{ "name" : "家", "page" : "" },
					{ "name" : "連絡先", "page" : "" }
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
    		birth:  new Date('1995-05-28')
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
