<template>
    <h1>I am Guest </h1>
    <p>My name is {{ name }}</p>
</template>

<script setup>
import {inject} from 'vue';
const name = inject("name")
</script>