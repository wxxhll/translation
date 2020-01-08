<template>
  <div class="translationOutput">
	
  </div>
</template>

<script>
export default {
  name: 'translationOutput',
  props:[
	"translatedText"
  ]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
	.translationOutput{
		border: 1px solid red;
		width: 100%;
		height: 40px;
		font-size: 26px;
		color: indianred;
		line-height: 40px;
		text-align: center;
		border-radius: 10px;
		background-color: #F5F5F5;
		margin: 0 auto;
	}
</style>
