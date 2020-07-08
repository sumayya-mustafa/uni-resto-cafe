<template>
	<div>
		<b-navbar id="header-conatiner">
			<b-navbar-brand href="#">{{ restuarant_name }}</b-navbar-brand>
			<cartIcon></cartIcon>
		</b-navbar>
	</div>
</template>
<script>
import cartIcon from './cartIcon.vue'
export default{
    components: {
    cartIcon
    },
    data() {
	return {
		restuarant_name:''
	}
	},
    mounted:function(){
      
    fetch('https://www.mocky.io/v2/5dfccffc310000efc8d2c1ad',{
    method:'get'
    })
      .then((response) => {return response.json()
      })
      .then((jsonData) => {
        this.restuarant_name = jsonData[0].restaurant_name
        console.log(jsonData)
       })
  }
}
</script>
<style>
	#header-conatiner{
	background-color: white!important;
    font-family: sans-serif;
    display: flex;
    justify-content: space-between;
    }
    #header-conatiner a{
    color:black!important;
    }
    #header-conatiner a:hover{
    color:#e22a2a!important;
    }
</style>