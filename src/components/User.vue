<script setup>
import { ref, reactive, toRefs } from 'vue';

const { userName } = defineProps({
    userName: {
        type: String
    }
})

const formsData = reactive({
    firstName: "",
    lastName: ""
})

const onSubmit = event => {
    event.preventDefault();
    console.log("data: ", toRefs(formsData));
}



</script>

<template>
    <div class="userClass">
        <form @submit="onSubmit">
            <input type="text" name="firstName" v-model="formsData.firstName" />
            <input type="text" name="lastName" v-model="formsData.lastName" />
            <button>Submit</button>
        </form>
    </div>
</template>

<style scoped>
.userClass {
    color: orange;
}
</style>