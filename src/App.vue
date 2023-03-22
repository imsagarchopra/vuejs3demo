<template>
  <!-- <HelloWorld msg="Vue JS 3 Demo" /> -->
  <!-- <vueForm/> -->
  <WatcherDemo/>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
//import vueForm from './components/vueForm.vue'
import WatcherDemo from './components/WatcherDemo'

export default {
  name: 'App',
  components: {
    //HelloWorld
    //vueForm
    WatcherDemo
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
  margin-top: 60px;
}
</style>
