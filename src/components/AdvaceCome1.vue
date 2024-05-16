<script setup>
const { messageFromParent } = defineProps({
    messageFromParent: String
});

const emitFromChild = defineEmits(['handleFromChild']);
emitFromChild('handleFromChild', "this message is from child!!")

</script>

<template>
    <p>Advance Component 1: {{ messageFromParent }}</p>

</template>
<style scoped></style>