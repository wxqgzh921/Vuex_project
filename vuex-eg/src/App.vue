<template>
	<div id="app">
		<Count></Count>
		<p>-----------------------------------------</p>
		<!--<router-link to="/cart">前往购物车</router-link>-->
		
	</div>
</template>

<script>
import Count from './components/Count'
import store from './store/store.js'
import Cart from './components/Cart'
	export default{
		name:'app',
	  // 把 store 对象提供给 “store” 选项，这可以把 store 的实例注入所有的子组件
		store,
		components:{
			Count,
			Cart
		}
	}
</script>
<style>
	#app{padding:10px;}
</style>