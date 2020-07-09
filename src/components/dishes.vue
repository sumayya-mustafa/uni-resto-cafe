<template>
<div>
<ul id="example-1">
  <li v-for="item in data" :key="item.dish_id">
    <div class="dish_detail_wrap">
      <div class="dish_detail">
            <div class="dish_name_detail">
            <p><b>{{ item.dish_name }}</b></p>
            <p><b>{{ item.dish_currency }}&nbsp;{{ item.dish_price }}</b></p>
            </div>
            <div class="dish_cal_detail">
            <p><b>{{ item.dish_calories }} calories</b></p> 
            </div>
      </div>
      <p class="dish_description">{{ item.dish_description }}</p><br>
      <dishButton class="dish_buttons"></dishButton> 
      <p v-if="item.addonCat.length" class="dish_custom_option"> Customizations Available </p>
    </div>
    <img :src="item.dish_image" class="dish_images">
  </li>
</ul>
</div>
</template>

<script>
import dishButton from './dishButton.vue' 
export default{
  props: ['data','store'],
  components: {
    dishButton
  },
  data() {
    return {
    categories: []
    }
  },
  mounted:function(){
    this.data.forEach((c)=>{
    console.log(c)
    })
  }
}
</script>
<style>
li{
  display: flex;;
  justify-content: space-between;
 
}
.dish_detail_wrap{
  display: flex;
  flex-direction: column;
  align-items: flex-start;
   padding-bottom: 10px;
}
.dish_detail{
  display: flex;;
  justify-content: space-between;
  width: 100%;
}
.dish_name_detail{
  display: flex;
  align-items: flex-start;
  flex-direction: column;
  text-align: left;
}
.dish_description{
  margin-top: 20px;
  text-align: left;
}
p{
  margin: 0px;
}
.dish_custom_option{
  color: #e22a2a;
  font-size: 15px;
  font-style: italic;
}
.dish_images{
  width: 200px;
  height: 200px;
}
@media (max-width: 991px){
  #menu_category_wrap ul{
    padding-left: 20px!important;
  }
  #menu_category_wrap li{
    font-size: 15px
  }
}
@media (max-width: 767px){
  .dish_images{
  width: 30vw;
  height: 30vw;
  }
  .dish_detail_wrap{
    padding-right: 15px;
  }
  #menu_category_wrap ul{
    display: flex;
    flex-direction: column;
    text-align: left;
    padding-left: 15px!important;
  }
  #menu_category_wrap li{
    padding-top: 10px!important;
    padding-bottom: 10px;
    font-size: 14px;
  }
  #menu_category_wrap a{
    border: none;
  }
  p{
    font-size: 15px;
  }
  .dish_custom_option{
    font-size: 13px;
  }

}
</style>
