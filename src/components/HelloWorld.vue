<template>
  <div class="hello">
    <h1>{{ msg }}</h1>  
  </div>
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

  <h2 v-if="num === 0">This is a zero</h2>
  <h2 v-else-if="num > 0">This is a Positive Number</h2>
  <h2 v-else-if="num < 0">This is a Negative Number</h2>
  <h2 v-else>This is Not a Number</h2>

  <h2 v-show="num === 0">This is not a zero</h2>

  <h2 v-for="name in names" :key="name">{{ name }}</h2>
  <h2 v-for="(name,index) in names" :key="name">{{ index }} {{ name }}</h2>

  <h2 v-for="name in fullNames" :key="name.first">{{ name.first }} {{ name.last }}</h2>

  <div v-for="actor in actors" :key="actor.name">
    <h2>{{ actor.name }}</h2>
    <h3 v-for="movie in actor.movies" :key="movie">{{ movie }}</h3>
  </div>

  <h2 v-for="(value, key, index) in myInfo" :key="value">{{ index }} {{ key }} - {{ value }}</h2>

  <template v-for="name in names" :key="name">
    <h2>{{ name }}</h2>
    <hr/>
  </template>

  <h2>Add Method - {{ add(1,2,3) }}</h2>
  <h2>Multiply Method - {{ multiply(baseValue) }}</h2>

  <h2>{{ count }}</h2>
  <div>
    <!-- <button v-on:click="count += 1">Increment</button> -->

    <!-- <button v-on:click="increment(1)">Increment</button>
    <button v-on:click="decrement(1)">Decrement</button> -->
 
    <button @click="increment(1,$event)">Increment</button>
    <button @click="decrement(1)">Decrement</button>
  </div>

  <h2>Computed Full Name - {{ fullName }}</h2>
  <button @click="changeFullName">Change Full Name</button>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
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
      },

      num: 0,

      names: ['Bruce', 'Clark', 'Diana'],
      fullNames:[
        {first: 'Bruce', last:'Wayne'},
        {first: 'Clark', last:'Kent'},
        {first: 'Princess', last:'Diana'}
      ],

      actors:[
       {
          name: 'Christian Bale',
          movies: ['Batman', 'The Prestige']
       },
       {
          name: 'Di Caprio',
          movies: ['Titanic', 'Inception']
       }
      ],

      myInfo:{
        name: 'Sagar',
        channel: 'ChopCode',
        course: 'Vue'
      },

      baseMultiplier: 5,
      baseValue: 2,

      count: 0,

      firstName: 'Bruce',
      lastName: 'Wayne'
    }
  },
  computed:{
    fullName: {
      get(){
        return `${this.firstName} ${this.lastName}`;
      },
      set(value){
        const names = value.split(' ');
        this.firstName = names[0];
        this.lastName = names[1];
      }
    }
  },
  methods:{
    add(a,b,c){
      return a+b+c;
    },
    multiply(num){
      return num * this.baseMultiplier;
    },
    increment(num,event){
      console.log(event);
       this.count += num;
    },
    decrement(num){
       this.count -= num;
    },
    changeFullName(){
      this.fullName = 'Clark Kent';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
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
