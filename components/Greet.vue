<script setup>
 const props = defineProps(['name', 'channel'])
</script>

<template>
    <h1 v-if="name" class="text-center">Hello {{ name }}</h1>
    
    <h1 v-if="channel" class="text-center">Channel {{ channel }}</h1>
</template>

