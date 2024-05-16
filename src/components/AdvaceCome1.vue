<script setup>
const { messageFromParent, handleChildEvent } = defineProps({
    messageFromParent: String,
    handleChildEvent: Function
});

const emitFromChild = defineEmits(['handleFromChild']);
emitFromChild('handleFromChild', "this message is from child!!")

</script>

<template>
    <p>Advance Component 1: {{ messageFromParent }}</p>
    <button @click="handleChildEvent('Data From Child 1')">Click Child Button 1</button>

</template>
<style scoped></style>