<template>
	<div class="count">
		<p>简单的vuex 计数</p>
		<p>{{ count }}</p>
		<p>
			<button @click="add">+</button>
			<button @click="reduce">-</button>
		</p>
	</div>
</template>
<script>
//import Store from '../store/store.js' (在当前页面上引入store,地下直接调用，如果在父组件引入store,则所有子组件都可用this.$store调用)

	export default{
		name:'count',
		computed:{                                                                                       
			count(){
				return this.$store.state.count;
			}
		},
		methods:{
			add(){
				this.$store.commit('add')
			},
			reduce(){
				this.$store.commit('reduce')
			}
		}
	}
</script>

<style>
	ul,li{ list-style: none;}
	.input{ width: 300px;height:20px;padding:5px;font-size: 14px;border-radius: 2px;border:1px solid #999;}
	.addBtn{height:30px; line-height:30px;margin-left:10px;}
</style>