<script setup>
import { reactive } from 'vue';

const myObject = reactive({
    title: "How to do lists in Vue",
    author: "Jane Doe",
    publishedAt: "2016-04-10"
})
</script>
<template>
    <ul>
        <li v-for="value in myObject">
            {{ value }}
        </li>
    </ul>
    <ul>
        <li v-for="(value, key) in myObject">
            {{ key }}: {{ value }}
        </li>
    </ul>
    <ul>
        <li v-for="(value, key, index) in myObject">
            {{ index }}. {{ key }}: {{ value }}
        </li>
    </ul>
    <ul>
        <li v-for="n in 10">
            {{ n }}
        </li>
    </ul>
    <ul>
        <template v-for="item in items">
            <li>{{ item.msg }}</li>
            <li class="divider" role="presentation"></li>
        </template>
    </ul>
    <ul>
        <li v-for="(value, key) in myObject" :key="key">
            {{ key }}: {{ value }}
        </li>
    </ul>

</template>