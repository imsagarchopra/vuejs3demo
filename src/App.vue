<template>
  <HelloWorld msg="Vue JS 3 Demo" />
  <!-- <vueForm/> -->
  <!-- <WatcherDemo/> -->

  <h2> App Component Username - {{ name }}</h2>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
//import vueForm from './components/vueForm.vue'
//import WatcherDemo from './components/WatcherDemo'

export default {
  name: 'App',
  components: {
    HelloWorld
    //vueForm
    //WatcherDemo
  },
  data(){
    return{
      name: 'Batman'
    }
  },
  provide(){
    return{
      userName: this.name
    }
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
