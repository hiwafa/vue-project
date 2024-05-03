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
      heroName: "My Hero Name"
    }
  },
  components: {
    HelloWorld
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
