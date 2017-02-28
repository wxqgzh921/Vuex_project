<template>
	<div class="cart">
	  <h3>Vuex购物车demo</h3>
	  <Shoplist></Shoplist>
	</div>
</template>
<script>
import Shoplist from './Shoplist'
//import store from '../store/cart/'
	export default{
		name:'cart',
		components:{
			Shoplist
		}
	}
</script>
<style>
	.cart{padding:10px;}
</style>