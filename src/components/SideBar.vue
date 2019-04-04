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
                <a @click="$emit('locale-select','es')" href="#">Español</a>
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
                    <li>
												<a href="#">{{ $t('link1') }}</a>
                    </li>
                    <li>
                        <a href="#">{{ $t('link2') }}</a>
                    </li>
                     <li>
                        <a href="#">{{ $t('link3') }}</a>
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
				"link1": "Academic Background",
				"link2": "Projects",
				"link3": "Contacts"
    },
    "pt": {
        "bio": "Biografia em português",
				"link1": "Percurso Académico",
				"link2": "Projetos",
				"link3": "Contactos"

    },
    "es": {
        "bio": "Biografía en español",
        "link1": "Recorrido Académico",
				"link2": "Proyectos",
				"link3": "Contactos"

    },
    "ja": {
        "bio": "日本語のビオグラフィ",
				"link1": "学歴",
				"link2": "家",
				"link3": "連絡先"

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
     
      }
  },
};
</script>

<style scoped lang="scss">
.sideBar {
  float: left;
  height: 100%;
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
