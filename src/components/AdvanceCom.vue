<script setup>
const emit = defineEmits(['response']);
</script>

<template>
    <div>Hi dear</div>
    <button @click="emit('response', 'This Message is From child')">Child Click</button>
</template>
<style scoped></style>