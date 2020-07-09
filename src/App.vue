<template>
  <div id="app">
   <Header></Header>
   <tabbedView></tabbedView>
  </div>
</template>
<script>
import Header from './components/header.vue'
import tabbedView from './components/tabbedView.vue'

export default {
  name: 'App',
  components: {
    Header,
    tabbedView
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
}
</style>