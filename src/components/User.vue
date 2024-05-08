<script setup>
const { userName } = defineProps(['userName'])
</script>

<template>
    <div class="userClass">Hi dear I am user {{ userName }}</div>
</template>

<style scoped>
.userClass {
    color: orange;
}
</style>