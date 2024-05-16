<template>
    <div class="advanceEnvironment">
        You learn: {{ topic }}

        <button @click="childClick('From Child')">Click Parent Function</button>

        <input :value="textValue" @input="hanldeTextBinding" placeholder="Type Here.." />
        <input v-model="textModel" placeholder="Type your text.." />
        <p>{{ textValue }}</p>
        <p>{{ textModel }}</p>

        <br />

        <button @click="handleToggle">Toggle Button</button>
        <p v-if="toggling">This text will be toggled</p>
        <p>Computed Data: {{ computedValue }} </p>
        <p ref="onMountData">Hello</p>

        <AdvanceCom @response="msg => {
            childMsg = msg;
        }" />
        <p>Child Message: {{ childMsg }}</p>

        <AdvaceCome1 messageFromParent="Hi this is a Message From Parent" @handleFromChild="msg => {
            childMsg2 = msg
        }" :handleChildEvent="hanldeChildClick" />
        <p>{{ childMsg2 }}</p>


        <AdvanceCom2>Hi: {{ childMsg2 }}</AdvanceCom2>

    </div>
</template>

<script setup>
import { ref, computed, onMounted, watch } from 'vue';


import AdvanceCom2 from './AdvanceCom2.vue';

import AdvaceCome1 from './AdvaceCome1.vue';
const childMsg2 = ref("No Message From child");
const hanldeChildClick = msg => {
    childMsg2.value = msg;
}

const childMsg = ref("No Message yet");
import AdvanceCom from './AdvanceCom.vue';



const onMountData = ref(null);

onMounted(() => {
    onMountData.value.textContent = "Component Mounted..."
});

watch(onMountData, (newValue) => {
    console.log("New Mounted Value: ", newValue.textContent);
});

const computedValue = computed(() => {
    return 10 + 10;
});

const toggling = ref(true);
const handleToggle = () => {
    toggling.value = !toggling.value;
}

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
    overflow: auto;
}
</style>