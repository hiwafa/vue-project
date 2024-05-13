<script setup>
import { ref, reactive, toRefs } from 'vue';

const { userName } = defineProps({
    userName: {
        type: String
    }
})

const formsData = reactive({
    firstName: "",
    lastName: "",
    plz: 0
})

const onSubmit = event => {
    // event.preventDefault();
    console.log("data: ", toRefs(formsData));
}



</script>

<template>
    <div class="userClass">
        <div v-once> this text will be rendered only one time</div>
        <div v-pre>

            public class JavaApp{
            --public static void main(String args[]){
            ----System.out.println("Hello World");
            --}
            }

        </div>
        <form @submit.prevent="onSubmit">
            <input type="text" name="firstName" v-model.trim.lazy="formsData.firstName" />
            <input type="text" name="lastName" v-model.trim="formsData.lastName" />
            <input type="number" name="zipCode" v-model.number="formsData.plz" />
            <button>Submit</button>
        </form>
        {{ formsData.firstName }}
        {{ formsData.lastName }}
    </div>
</template>

<style scoped>
.userClass {
    color: orange;
}
</style>