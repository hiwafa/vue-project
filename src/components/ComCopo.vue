<script setup>
    import {ref, reactive} from "vue";

    const message = ref("Com Hello World");
    const counter = reactive({
        count: 110
    });

    /*
    

    // options api
    export default {
        name: "ComponentName",
        data(){
            return {
                var1: "value 1"
            }
        }
    }


    composition api
    import {ref} from "vue";
    const var1 = ref("value 1");
    
    */


    const users = ref([
        {id: 1, name: "Name 1"},
        {id: 2, name: "Name 2"},
        {id: 3, name: "Name 3"},
        {id: 4, name: "Name 4"},
        {id: 5, name: "Name 5"},
        {id: 6, name: "Name 6"},
        {id: 7, name: "Name 7"},
    ]);

    const myVars = reactive({
        isLoggedin: false,
        numberOfusers: 11,
        isShow: true
    })


</script>

<template>

   {{message}}
   {{counter.count}}

   <ul><li v-for="user in users" :key="user.id">{{user.name}}</li></ul>

    <h1 v-if="myVars.isLoggedin">You are logged in</h1>
    <h1 v-else-if="myVars.numberOfusers == 1">the number of users {{myVars.numberOfusers}}</h1>
    <h1 v-else>There is no true condition</h1>

    <h1 v-show="myVars.isShow">Showable!!!!!</h1>
    
    <h2 v-bind:style="[{color: 'green'}, {backgroundColor: 'yellow'}]">Vue Style</h2>
    <h2 :style="1 === 1 && {color: 'blue'}">Vue Style 2</h2>

    <h3 :class="{
        italicClass: myVars.isShow
    }">I am italic text</h3>

</template>

<style scoped>

.italicClass {
    font-style: italic
}
</style>