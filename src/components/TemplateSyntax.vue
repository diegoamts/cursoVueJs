<script setup>
    const dynamicId = 1
</script>

<template>
    <div v-bind:id="dynamicId">
        Meu id dinâmico: {{ dynamicId }}
    </div>
</template>