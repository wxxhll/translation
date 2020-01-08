<template>
  <div id="app" class="container">
	<h1 class="page-header">在线翻译</h1>
	<h5 class="text-meted">简单 / 易用 / 便捷</h5>
    <translationFrom v-on:formSubmit="translationText"></translationFrom>
	<translationOutput v-text="translatedText"></translationOutput>
  </div>
</template>

<script>
import TranslationFrom from './components/TranslationFrom.vue'
import TranslationOutput from './components/TranslationOutput.vue'
export default {
  name: 'app',
  data:function(){
	return{
		translatedText:"",
	}
  },
  components: {
	TranslationFrom,
	TranslationOutput
  },
  methods:{
	translationText:function(text,language){
		// alert(text,language);
		this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20200108T030249Z.4e14405a65ad84bc.9b93c4494414ace92746129ab34694a8b61b5c23&lang='+language+'&text='+text)
		.then(function(response){
			this.translatedText = response.body.text[0];
		})
		// this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/getLangs?key=trnsl.1.1.20200108T030249Z.4e14405a65ad84bc.9b93c4494414ace92746129ab34694a8b61b5c23&lang='+language+'&text='+text)
		// .then(function(response){
		// // console.log(response);
		// this.translatedText = response.body.text[0];
		// })
	}
  }
}
</script>

<style>
	
</style>
