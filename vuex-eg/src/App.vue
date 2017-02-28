<template>
	<div id="app">
		<Count></Count>
		<p>-----------------------------------------</p>
		
	</div>
</template>

<script>
import Count from './components/Count'
import store from './store/store.js'

	export default{
		name:'app',
	  // 把 store 对象提供给 “store” 选项，这可以把 store 的实例注入所有的子组件
        store,
		components:{
			Count
		}
	}
</script>
<style>
	#app{padding:10px;}
</style>