<template>
    <h1 style="color:blue; background:violet">Hello 1</h1>
    <h1 v-bind:style="{color:'black', backgroundColor:'pink'}">Hello 2</h1>
    <h1 v-bind:style="{color:'black', 'background-color':'yellow'}">Hello 3</h1>
    <h1 :style="{color:'black', 'background-color':'orange'}">Hello 4</h1>


    <!-- BInding to  Object -->
    <h1 v-bind:style="{color:cl, background:bg}">Hello 5</h1>
    <h1 v-bind:style="styleObj">Hello 6</h1>

    <h1 v-bind:style="[styleObj, styleObj2]">Hello 7</h1>

    <!-- BInding to array -->
</template>

<script setup>
    import { ref, reactive } from "vue";
    const cl = ref("yellow");
    const bg = ref("green");

    const styleObj = reactive({
        color:"pink",
        background:"indigo",
    })
    const styleObj2 = reactive({
        "font-size":"20px",
        "font-weight":"bold",
    })

</script>
<style></style>