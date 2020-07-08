<template>
	<div class="cart_icon_outer_wrap">
	<p>My Orders</p>
	<div class="cart_icon_wrap">
	<i class="fa" style="font-size:24px">&#xf07a;</i>
    <span class='badge badge-warning' id='lblCartCount'>{{cartcount}}</span>	
	</div>
	</div>
</template>
<script>
export default {
	computed:{
		cartcount(){
			return this.$store.state.cartcount;
		}
	}
}
</script>
<style scoped>
#lblCartCount {
    font-size: 12px;
    background: #ff0000;
    color: #fff;
    padding: 0 5px;
    vertical-align: top;
    margin-left: -10px;
}
.badge {
  padding-left: 9px;
  padding-right: 9px;
  -webkit-border-radius: 9px;
  -moz-border-radius: 9px;
  border-radius: 9px;
}

.label-warning[href],
.badge-warning[href] {
  background-color: #c67605;
}
.cart_icon_outer_wrap{
display: flex;
padding-top: 20px;
}
p{
padding-right: 10px;
}

</style>
