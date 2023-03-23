<template>
  <!-- <HelloWorld msg="Vue JS 3 Demo" /> -->
  <!-- <vueForm/> -->
  <!-- <WatcherDemo/> -->

  <!-- <h2> App Component Username - {{ name }}</h2> -->

  <button @click="showPopup=true">Open Popup</button>
  <!-- <PopUp v-show="showPopup" @close="showPopup = false"/> -->
  <PopUp v-show="showPopup" @close="closePopup"/>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
//import vueForm from './components/vueForm.vue'
//import WatcherDemo from './components/WatcherDemo'
import PopUp from './components/PopUp.vue'

export default {
  name: 'App',
  components: {
    //HelloWorld
    //vueForm
    //WatcherDemo
    PopUp
  },
  data(){
    return{
      name: 'Batman',
      showPopup: false     
    }
  },
  provide(){
    return{
      userName: this.name
    }
  },
  methods:{
    closePopup(name){
      this.showPopup = false;
      console.log('name', name);
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
