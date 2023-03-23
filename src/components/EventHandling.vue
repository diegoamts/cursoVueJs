<script setup>
    import { ref } from 'vue';

    const count = ref(0)

    const name = ref("Vue.js")

    function greet(event){
        alert(`Hello ${name.value}`)

        if(event){
            alert(event.target.tagName)
        }
    }

    const say = (message) => {
        alert(message)
    }

</script>
<template>
    <button @click="count++">
        Add 1
    </button>
    <p>Count is: {{ count }}</p>
    <button @click="greet">
        Greet
    </button>
    <button @click="say('hello')">
        Say Hello!
    </button>
</template>