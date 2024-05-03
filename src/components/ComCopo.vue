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

</script>

<template>

   {{message}}
   {{counter.count}}
</template>