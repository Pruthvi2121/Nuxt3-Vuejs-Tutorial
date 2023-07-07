<template>
    <h1 class="text-center font-bold">I am  parent</h1>
    <div class="text-center">
        <User/>
    </div>
</template>

<script setup>
import {provide} from 'vue';
provide("name","Jonny")
</script>