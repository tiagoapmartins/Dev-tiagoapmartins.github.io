<template>
    <div class="sideBar">
        <ul class="langSelect">
            <li>
                <a href="#">English</a>
            </li>
            <li>
                <a href="#">Português</a>
            </li>
            <li>
                <a href="#">Español</a>
            </li>
            <li>
                <a href="#">日本語</a>
            </li>
        </ul>
        <div>
            <img src="../assets/me.jpg">
        </div>
        <div>
            <h2 class="name">Tiago Martins</h2>
            <h4 v-if="lang=='jp'" class="pronunciation">ティアゴ　マルチンス</h4>
            <p class="shortBio">
                {{ bio }}
            </p>
        </div>
        <div>
            <nav>
                <ul>
                    <li>
                        <a href="#">Academics</a>
                    </li>
                    <li>
                        <a href="#">Projects</a>
                    </li>
                     <li>
                        <a href="#">Contacts</a>
                    </li>
                </ul>
            </nav>
        </div>
    </div>
</template>

<script>
export default {
  name: "SideBar",
  props: {
    lang: String, 
    bio: String
  },
  data: {
    en_bio: 'Default bio in English',
    pt_bio: 'Biografia Portuguesa',
    es_bio: 'Biografia en Español',
    jp_bio: '日本語のビオぐらふぃ'
  }
};
</script>

<style scoped lang="scss">
.sideBar {
    float: left;
    height: 100%;
    background: #151515;
}
img {
     border-radius: 50%;
     max-width: 300px;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>      
