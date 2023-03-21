<script setup>
    import { ref, computed } from 'vue';

    const isActive = ref(true)
    const error = ref(null)

    const classObject = computed(() => ({
        active: isActive.value && !error.value,
        'text-danger': error.value && error.value.type === 'fatal'
    }))

</script>
<template>
    <div :class="classObject">
        Meu teste
    </div>
</template>