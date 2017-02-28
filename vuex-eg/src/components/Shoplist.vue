<template>
	<div class="shoplist">
		<h4>商品信息</h4>
		<table class="table table-hover table-bordered table-shop">
			<thead>
				<tr>
					<th>id</th>
					<th>名称</th>
					<th>价格</th>
					<th>数量</th>
					<th>actions</th>
				</tr>
			</thead>
			<tbody>
				<tr v-for="(shop,index) in shop_list">
					<td>{{ shop.id }}</td>
					<td>{{ shop.name }}</td>
					<td>{{ shop.price }}</td>
					<td>{{ shop.num ||'' }}</td>
					<td>
						<div @click ="add_db(shop)" class="btn btn-info">{{ shop.num ? '+' : '加入购物车'}}</div>
						<div @click="reduce_db(shop)" class="btn btn-warning" v-if="shop.num && shop.num > 0">-</div>
					</td>
				</tr>
			</tbody>
		</table>
	</div>
</template>
<script>
	export default{
		name:'shoplist',
		data(){
			return{
				shop_list:[
					{
					 id:1,
					 name:'鱼香肉丝',
					 price:12
					},
					{
				     id:2,
				     name:'宫保鸡丁',
				     price:14
					},
					{
					 id:3,
					 name:'土豆丝',
					 price:10
					},
					{
					 id:4,
					 name:'米饭',
					 price:2
					}
				]
			}
		}
//		mounted(){
//		/**
//      * 初始化时把购物车的菜品数量绑定到菜品列表中
//      */
//	        var list = this.$store.state.cart.cartList;
//	        for(var i ;i<this.shop_list.length;i++){
//	        	for(var j;j< list.length;j++){
//	        		if(list[j].id == this.shop_list[i].id){
//	        			this.$set(this.shop_list,i,list[j]);
//	        			break;
//	        		}
//	        	}
//	        }
//		},
//		methods:{
//		    /**
//	         * 点击菜品列表中的加号
//	         */
//      	add_db(shop){
//      		var id = shop.id;
//      		 //检测是否存在购物车中,如果存在修改state.curState为true,并设置state.curIndex为当前菜品在购物车中的索引
//      		this.$store.dispatch('check_db',{
//      			id
//      		});
//      		//如果存在,先自增当前菜品中的num，再设置购物车的数量
//          	//如果不存在，直接往购物车中push一个新的菜品
//          	if(this.$store.state.cart.curIndex !=-1){
//          		this.$store.dispatch('add_db');
//          	}else{
//          		this.$set(shop,'num',1);
//          		this.$store.dispatch('create_db',{shop});
//          	}
//      	},
//      	/**
//	         * 点击菜品列表中的减号
//	         */
//	        reduce_db(shop){
//	        	var id = shop.id;
//	        	this.$store.dispatch('check_db',{id});
//	        	shop.num = parseInt(shop.num);
//	        	this.$store.dispatch('reduce_db');
//	        }
//      
//		}
	}
</script>
<style>
	/*.table{width:100%;border:1px solid #000;}
	.table thead tr{ border-bottom:1px solid #000;}*/
	.table-shop th{ text-align:center;}
	.table-shop td{ text-align:center;}
</style>