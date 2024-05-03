<script>

import ComCopo from "./ComCopo.vue"

export default{
    name: "HelloWorld",
    props: ['msg', "heroName"],
    components: {
        ComCopo
    }
}

</script>

<template>

    <ComCopo />
    <div> This is Hello world Component: {{msg}} - {{heroName}}</div>
    
</template>