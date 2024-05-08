<script setup>
import { ref } from 'vue';

const { userName } = defineProps({
    userName: {
        type: String
    }
})

const nameUser = ref("");

const onSubmit = event => {
    event.preventDefault();
    console.log("event: ", event);
}

</script>

<template>
    <div class="userClass">
        <form @submit="onSubmit">
            <input type="text" name="nameUser" v-model="nameUser" />
            <button>Submit</button>
        </form>
    </div>
</template>

<style scoped>
.userClass {
    color: orange;
}
</style>