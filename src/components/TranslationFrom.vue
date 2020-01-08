<template>
  <div class="translationFrom container">
	<form v-on:submit="formSubmit" class="">
		<div class="well">
			<input type="text" v-model="translationText" class="form-control" placeholder="请输入需要翻译的内容" />
			<br>
			<select class="form-control" v-model="language">
				<option value="en">English</option>
				<option value="ru">Russian</option>
				<option value="ko">Korean</option>
				<option value="eu">Basque</option>
				<option value="ja">Japanese</option>
				<option value="jv">Javanese</option>
			</select>
			<br>
			<button type="submit" class="btn btn-primary" value="翻译">翻译</button>
		</div>
	</form>
  </div>
</template>

<script>
export default {
  name: 'translationFrom',
  data:function(){
	return{
		translationText:"",
		language:""
	}
  },
  methods:{
	formSubmit:function(e){
		// alert(this.translationText);
		this.$emit("formSubmit", this.translationText, this.language);
		e.preventDefault();
	}
  },
  created:function(){
	this.language = "en";
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
