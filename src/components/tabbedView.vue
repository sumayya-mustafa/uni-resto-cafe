<template>
  <div>
    <b-tabs  id="menu_category_wrap">
        <b-tab v-for="item in categories" v-bind:key="item.menu_category_id" :title="item.menu_category">
          <dishes  :data="item.category_dishes"></dishes>
        </b-tab>
    </b-tabs>
  </div>
</template>

<script>
import Dishes from './dishes.vue'
export default{
    
    components: {
     Dishes
  },
  data() {
    return {
    categories: []
      
    }
  },
  mounted:function(){
      
    fetch('https://www.mocky.io/v2/5dfccffc310000efc8d2c1ad',{
    method:'get'
    })
      .then((response) => {return response.json()
      })
      .then((jsonData) => {
          console.log(jsonData)
        this.categories = jsonData[0].table_menu_list;
        
    })
  }
}
</script>

<style>

#menu_category_wrap li{
border-left: 0px;
border-right: 0px;
border-top: 0px;
border-bottom: solid 1px #ddd!important;
margin-right: 0px!important;
list-style: none;
padding-top: 20px; 
font-style: bold; 
}
#menu_category_wrap li:hover{
border-bottom-color:#e22a2a!important;
}
#menu_category_wrap li a{
  color:black!important;
}
#menu_category_wrap li a:hover {
color: #e22a2a!important;
text-decoration: none;
}
#menu_category_wrap ul{
  padding-left: 25px;
}

</style>
