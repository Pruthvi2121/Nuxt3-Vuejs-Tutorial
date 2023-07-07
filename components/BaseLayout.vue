<script setup>

</script>
<template>
    <!-- Named slot -->
    <h1>Base Layout</h1>

    <slot name="header"></slot>
    <slot name="main"></slot>
    <slot name="footer"></slot>

    <!-- this is default -->
    <slot></slot>
</template>