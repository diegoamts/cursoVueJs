<script>
import { ref, onMounted } from 'vue';

const input = ref(null)

onMounted(() =>{
    input.value.focus()
})

</script>
<template>
    <input ref="input">
</template>