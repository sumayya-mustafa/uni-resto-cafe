<template>
  <div>
    <tabs>
        <tab v-for="item in categories" v-bind:key="item.menu_category_id" :name="item.menu_category">
            <dishes  :data="item.category_dishes"></dishes>
        </tab>
    </tabs>
  </div>
</template>

<script>
import {Tabs,Tab} from 'vue-tabs-component';
import Dishes from './dishes.vue'
export default{
    //props: ['store'],
    components: {
    Tabs,Tab, Dishes
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
        this.categories = jsonData[0].table_menu_list
      })
  }
}
</script>

<style>
.tabs-component {
  margin: 4em 0;
  margin-top: 0px!important
}

.tabs-component-tabs {
  border: solid 1px #ddd;
  border-radius: 6px;
  margin-bottom: 5px;
}

@media (min-width: 700px) {
  .tabs-component-tabs {
    border: 0;
    align-items: stretch;
    display: flex;
    justify-content: flex-start;
    margin-bottom: -1px;
  }
}

.tabs-component-tab {
  color: #999;
  font-size: 14px;
  font-weight: 600;
  margin-right: 0;
  list-style: none;
}

.tabs-component-tab:not(:last-child) {
  border-bottom: dotted 1px #ddd;
}

.tabs-component-tab:hover {
  color: #666;
}

.tabs-component-tab.is-active {
  color: #000;
}

.tabs-component-tab.is-disabled * {
  color: #cdcdcd;
  cursor: not-allowed !important;
}

@media (min-width: 700px) {
  .tabs-component-tab {
    background-color: #fff;
    border: solid 1px #ddd;
    border-radius: 3px 3px 0 0;
    margin-right: .5em;
    transform: translateY(2px);
    transition: transform .3s ease;
  }

  .tabs-component-tab.is-active {
    border-bottom: solid 1px #fff;
    z-index: 2;
    transform: translateY(0);
  }
}

.tabs-component-tab-a {
  align-items: center;
  color: inherit;
  display: flex;
  padding: .75em 1em;
  text-decoration: none;
}

.tabs-component-panels {
  padding-top:   20px!important;
}

@media (min-width: 700px) {
  .tabs-component-panels {
    border-top-left-radius: 0;
    background-color: #fff;
    border: solid 1px #ddd;
    border-radius: 0 6px 6px 6px;
    box-shadow: 0 0 10px rgba(0, 0, 0, .05);
    padding: 4em 2em;
  }
}
.tabs-component ul{
padding-left: 0px;
}
.tabs-component li{
border-left: 0px;
border-right: 0px;
border-top: 0px;
border-bottom: solid 1px #ddd!important;
margin-right: 0px!important;
list-style: none;
padding-top: 20px;  
}
.tabs-component li:hover{
border-bottom-color:#e22a2a!important;
}
.tabs-component li a:hover {
color: #e22a2a;
text-decoration: none;
}

</style>
