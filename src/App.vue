<template>
  <teleport to="portal-root">
    <!-- <HelloWorld msg="Vue JS 3 Demo" /> -->
    <h2> Hello</h2>
  </teleport>
  
  <!-- <vueForm/> -->
  <!-- <WatcherDemo/> -->

  <!-- <h2> App Component Username - {{ name }}</h2> -->

  <!-- <button @click="showPopup=true">Open Popup</button> -->
  <!-- <PopUp v-show="showPopup" @close="showPopup = false"/> -->
  <!-- <PopUp v-show="showPopup" @close="closePopup"/> -->

  <!-- <CardComponent>Card Content 1</CardComponent>
  <CardComponent><h2>Card Content 2</h2></CardComponent>

  <CardComponent> 
    <template v-slot:header>
      <h3>Header</h3>
    </template>
    <template v-slot:default>
      <h3>Default Content</h3>
    </template>
    <template v-slot:footer>
      <h3>Footer</h3>
    </template>
  </CardComponent> -->

  <!-- <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.firstName }} {{ slotProps.lastName }}
    </template>
  </NameList> -->

  <!-- <button @click="activeTab='TabA'">Tab A</button>
  <button @click="activeTab='TabB'">Tab B</button>
  <button @click="activeTab='TabC'">Tab C</button> -->

  <!-- <TabA v-if="activeTab === 'TabA'"/>
  <TabB v-if="activeTab === 'TabB'"/>
  <TabC v-if="activeTab === 'TabC'"/> -->

  <!-- <keep-alive>
    <component :is="activeTab"/>
  </keep-alive> -->

  <!-- <PostList/>
  <CreatePost/> -->

  <!-- <TemplateRef/> -->

  <!-- <DataComponent/> -->
  <!-- <MethodsComponent/> -->

  <!-- <VModel/> -->

  <ComputedComponent/>

</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
//import vueForm from './components/vueForm.vue'
//import WatcherDemo from './components/WatcherDemo'
//import PopUp from './components/PopUp.vue'
//import CardComponent from './components/CardComponent.vue';
//import NameList from './components/NameList.vue';

// import TabA from './components/TabA.vue';
// import TabB from './components/TabB.vue';
// import TabC from './components/TabC.vue';
//import CreatePost from './components/CreatePost.vue';
//import PostList from './components/PostList.vue';

// import TemplateRef from './components/TemplateRef.vue';
//import DataComponent from './components/DataComponent.vue';
//import MethodsComponent from './components/MethodsComponent.vue'

// import VModel from './components/VModel.vue';

import ComputedComponent from './components/ComputedComponent.vue';

export default {
  name: 'App',
  components: {
    //HelloWorld
    //vueForm
    //WatcherDemo
    //PopUp
    //CardComponent
    //NameList
    // TabA,
    // TabB,
    // TabC,

    //PostList,
    //CreatePost

    //TemplateRef

    //DataComponent
    //MethodsComponent

    //VModel

    ComputedComponent
    
},
  data(){
    return{
      name: 'Batman',
      showPopup: false,
      activeTab:'TabA'
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
