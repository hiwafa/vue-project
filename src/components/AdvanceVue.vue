<template>
    <div class="advanceEnvironment">
        You learn: {{ topic }}

        <button @click="childClick">Click Parent Function</button>

    </div>
</template>

<script setup>

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