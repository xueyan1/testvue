<template>
		<div>
			<div>
				<input v-model="inputValue"/>
				<button @click="submit">提交</button>
			</div>
			<ul>
				<todoitem 
				v-for="(item, index) of list" 
				:key="index"
				:content="item"
				:index="index"
				@delete="handleDelete"
				></todoitem>
			</ul>
		</div>
</template>

<script>
 import todoitem from './components/todoItem.vue'
 
export default {
	components:{
		"todoitem":todoitem
	},
  data(){
		return {
			inputValue :'',
			list:[]
		}
	},
	methods:{
		submit(){
			if(!this.inputValue) return
			this.list.push(this.inputValue)
			this.inputValue = ''
		},
		handleDelete(index){
			console.log(index)
			this.list.splice(index,1)
		}
	}
}
</script>

<style scoped>
	
</style>
