<script lang="ts">
import HelloWorld  from "./components/HelloWorld.vue";
export default {
  name: "App",
  data(){
    return {
      message: "Hello world with vue.js",
      txt: "this is text binding <h1> Hello </h1>",
      htmlTxt: "this is an html text binding <h1> Hello </h1>",
      id1: "redText",
      bld: "boldText",
      heroName: "My Hero Name",
      counter: 0,
      userInput: ""
    }
  },
  components: {
    HelloWorld
  },
  methods: {
    increment(){
      this.counter++;
    },

    getMethodCounter(){
      return this.counter
    }
  },
  computed: {
    getComputedCounter(){
      return this.counter;
    }
  },
  watch: {
    counter(newValue, oldValue){
      if(newValue > oldValue && newValue === 15) alert("reached 15")
    }
  }
}

</script>

<template>
  <div class="wrapper">

   {{ message }}

  <p v-text="txt"></p>
  <p v-html="htmlTxt"></p>
  <p v-bind:id="id1">This is a red text</p>
  <p :id="id1" :class="bld" class="fntSize">This is a red text</p>

  <button v-on:click="increment">Click Me1: {{counter}}</button>
  <button @click="counter--">Click Me2: {{counter}}</button>
  <p>Get from methods: {{getMethodCounter()}}</p>
  <p>Get from computed: {{getComputedCounter}}</p>
  <input id="userInput" type="text" v-model="userInput" />
  {{userInput}}
  <br/>

  <HelloWorld msg="Hi from Parent" :hero-name="heroName"/>

  </div>
</template>

<style scoped>
  #redText{
    color: red;
  }
  .boldText {
    font-weight: bold;
  }
  .fntSize {
    font-size: 50px;
  }
</style>
