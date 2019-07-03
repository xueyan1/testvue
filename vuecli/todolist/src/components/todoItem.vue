<template>
	<li @click="handleClick"> {{content}} </li>
</template>

<script>
	export default {
		props:['content','index'],
		data(){
			return{
				
			}
		},
	methods:{
		handleClick(){
			console.log(this.index)
			this.$emit("delete",this.index)
		}
	}
	}
</script>

<style >
</style>
