<template>
	<div class="would-you-rather">
		<h3>Would you rather...</h3>
		<h4><span :v-model="id">{{id+1}}.</span>  {{ question }}</h4>
    	<div class="radio">
			<label>
      			<input type="radio" :value="answer1" v-model="selection">
      				{{answer1}}
    		</label>
		</div>
    	<div class="radio">
			<label>
      			<input type="radio" :value="answer2" v-model="selection">
      				{{answer2}}
    		</label>
  		</div>
    </div>
</template>

<script>
export default {
	name: 'ComponentQuestion',
	props: {
		id:0,
		question: String,
		answer1: String,
		answer2: String,
		
	},
	data() {
		return {
			selection: '',
			
		}
	},
	watch: {
		
		selection() {
			this.$emit('selection-changed', this.selection, this.id)
		}
	},
}
</script>

<style>
.would-you-rather{
    display: block;
	padding-left: 10px;
   background-image: linear-gradient(green, yellow);
}
</style>