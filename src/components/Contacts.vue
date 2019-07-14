<template>
    <div class="contacts">
    	<h2>{{ $t('title')  }}</h2>
			<div class="contacts-cont">
				<p>
					{{ $t('cont-text') }}	
				</p>
				<span><i class="fa fa-envelope"></i> E-MAIL: <a href="mailto:tiago.a.p.martins@protonmail.ch?Subject=Work%20Proposal">tiago.a.p.martins@protonmail.ch</a></span>
				<span><i class="fab fa-linkedin"></i> Linkedin: <a href="https://www.linkedin.com/in/tiagoapmartins/">tiagoapmartins</a></span>
				<span><i class="fab fa-github"></i> Github: <a href="https://github.com/RIPASSAS">RIPASSAS</a></span>
			</div>
    </div>
</template>

<i18n>
{
    "en": {
       	"title": "Contacts",
				"cont-text": "I'm open to any offers and willing to relocate."
		},
    "pt": {
        "title": "Contactos",
				"cont-text": "Estou aberto a todas a oportunidades e disposto a relocar-me"
		},
    "ja": {
				"title": "連絡先"
		}
}
</i18n>

<script>
export default {
  name: "Contacts",
  props: {
    
  },
  data () {
  	return {
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
.contacts {
	padding-top: 0px;
	padding-left: 30px;
	text-align: left;
}

.contacts-cont {
	position: relative;
	padding: 10px 10px 30px 20px;
	margin: 30px 10px 30px 0;
	background-color: #ccc;
	border-radius: 15px;
}

.contacts-cont span {
	display: block;
	padding: 5px 0;
}

a {
  color: #42b983;
  text-decoration: none;
}
</style>
