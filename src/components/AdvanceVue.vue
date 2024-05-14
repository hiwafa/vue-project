<template>
    <div class="advanceEnvironment">
        You learn: {{ topic }}

        <button @click="childClick('From Child')">Click Parent Function</button>

        <input :value="textValue" @input="hanldeTextBinding" placeholder="Type Here.." />
        <input v-model="textModel" placeholder="Type your text.." />
        <p>{{ textValue }}</p>
        <p>{{ textModel }}</p>


    </div>
</template>

<script setup>

import { ref } from 'vue';

const textValue = ref("");
const textModel = ref("");

const hanldeTextBinding = event => {
    textValue.value = event.target.value;
}



const { topic, childClick } = defineProps({
    topic: String,
    childClick: Function
});

</script>

<style scoped>
.advanceEnvironment {
    border: 1px solid lightblue;
    width: 100%;
    height: 300px;
}
</style>