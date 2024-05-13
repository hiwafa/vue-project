<script>

import ComCopo from "./ComCopo.vue"

export default {
    name: "HelloWorld",
    props: ['msg', "heroName"],
    components: {
        ComCopo
    },

    data() {
        return {
            myName: "Wafa"
        }
    },
    methods: {
        displayData() {

            this.setter = "New Set Value 9999";
            return this.setter
        }
    },
    computed: {
        computedFunc() {
            return "This is a computed function"
        },
        setter: {
            get() {
                return "This is the data returned from a method"
            },
            set(val) {
                console.log("New Value: ", val)
            }
        }
    },
    watch: {
        myName: {
            handler(newVal) {
                console.log("My Name is has changed:", newVal)
            },
            immediate: true,
            deep: true
        }
    }
}

</script>

<template>

    <ComCopo />
    <div> This is Hello world Component: {{ msg }} - {{ heroName }}</div>
    <div>{{ displayData() }}</div>
    <div>{{ computedFunc }}</div>
    <input type="text" v-model="myName">
    <p>{{ myName }}</p>
    <p>{{ setter }}</p>

</template>