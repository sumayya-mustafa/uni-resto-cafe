<template>
	<div>
	<b-button-group class="custom_button_group">
      <b-button v-on:click="plusButtonClick" id="plus-button">+</b-button>
      <b-button disabled id="count-button">{{ count }}</b-button>
      <b-button v-on:click="minusButtonClick" id="minus-button">-</b-button>
    </b-button-group>
  </div>
</template>
<script>
export default{
data() {
	return{
		count:0
	}
},
methods:{
plusButtonClick: function(){
this.$store.state.cartcount++;	
this.count = this.count + 1;
console.log(this.count)
return this.count
},
minusButtonClick: function(){
this.$store.state.cartcount--;
this.count = this.count - 1;
console.log(this.count)
return this.count
}
}
}
</script>
<style scoped>
#plus-button{
border-radius: 50px 0px 0px 50px;
padding-left: 25px;
padding-right: 25px;
background-color: #28a745;
border-color:#28a745;
}
#count-button{
padding: 0px 25px;
background-color: #28a745!important;
opacity: 1;
border-color:#28a745;
}
#minus-button{
border-radius: 0px 50px 50px 0px;
padding-left: 25px;
padding-right: 25px;
background-color: #28a745;
border-color:#28a745;
}
</style>
