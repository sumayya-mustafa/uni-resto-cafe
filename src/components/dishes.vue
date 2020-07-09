<template>
<div>
<ul id="example-1">
  <li v-for="item in data" :key="item.dish_id">
    <div class="dish_detail_wrap">
      <div class="dish_detail">
            <div class="dish_name_detail">
            <p><b>{{ item.dish_name }}</b></p>
            <p><b>{{ item.dish_currency }}{{ item.dish_price }}</b></p>
            </div>
            <div class="dish_cal_detail">
            <p><b>{{ item.dish_calories }} calories</b></p> 
            </div>
      </div>
      <p class="dish_description">{{ item.dish_description }}</p><br>
      <dishButton class="dish_buttons"></dishButton> 
      <p v-if="item.addonCat.length" class="dish_custom_option"> Customizations Available </p>
    </div>
    <!-- <div class="dish_images" style="background-image: url(item.dish_image)"></div> -->
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
<style scoped>
li{
  display: flex;;
  justify-content: space-between;
  padding-bottom: 20px;
}
.dish_detail_wrap{
  display: flex;
  flex-direction: column;
  align-items: flex-start;
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
}
.dish_description{
  margin-top: 20px;
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

</style>
