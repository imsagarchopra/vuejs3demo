<template>
  <HelloWorld msg="Vue JS 3 Demo" />
  <div>{{ greet }}</div>
  <div v-text="name"></div>

  <div v-html="channel"></div>

  <h1 v-bind:id="headingId">Heading</h1>
  <button v-bind:disabled="isDisabled">Bind</button>

  <h2 class="underline">Underlined text</h2>
  <h2 class="underline" v-bind:class="'new'">Combination of static and dynamic class</h2>

  <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h2 v-bind:class="isSoldOut ? 'soldOut' : 'new'">Sold Out?</h2>

  <h2 v-bind:class="['new', 'promoted']">Newly Promoted Array movie</h2>
  <h2 v-bind:class="[isPromoted && 'promoted', isSoldOut ? 'soldOut' : 'new']">Array Conditional movie</h2>

  <h2 v-bind:class="{
    promoted: isPromoted,
    new: !isSoldOut,
    soldOut: isSoldOut
  }">Object Conditional movie</h2>

  <h2 v-bind:style="{
    color: highlightColor,
    fontSize: headerSize + 'px',
    padding: '20px'
  }">Inline Style</h2>
  <h2 v-bind:style="headerStyleObject">Style Object</h2>
  <h2 v-bind:style="[baseStyleObject, successStyleObject]">Success Style Array</h2>
  <h2 v-bind:style="[baseStyleObject, dangerStyleObject]">Danger Style Array</h2>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      greet: "Hello",
      name: "Shaggy",
      channel: "<b>Youtube</b>",
      headingId: "heading",
      isDisabled: true,
      isPromoted: true,
      isSoldOut: true,
      highlightColor: 'orange',

      headerSize: 50,
      headerStyleObject: {
        color: 'orange',
        fontSize: '50px',
        padding: '20px'
      },
      baseStyleObject: {
        fontSize: '50px',
        padding: '10px'
      },
      successStyleObject: {
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px solid green'
      },
      dangerStyleObject: {
        color: 'darkred',
        backgroundColor: 'red',
        border: '1px solid red'
      }
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

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.new {
  color: green;
}

.soldOut {
  color: red;
}
</style>
