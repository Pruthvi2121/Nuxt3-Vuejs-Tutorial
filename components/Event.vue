<script setup>
const name = ref("")

</script>
<template>
    <div class="flex flex-col my-2">
        <!-- <button  @click="$emit('increaseCount')"  class="mx-auto bg-slate-300 px-2 py-1 rounded">Increase</button> -->
        <!-- passing Argument -->
        <!-- <button  @click="$emit('increaseCount', 11)" class="mx-auto bg-slate-300 px-2 py-1 rounded">Increase by 11</button> -->
    </div>
    

    <div class="text-center ">
        <!-- Event Validation -->
        
        <form @submit.prevent="$emit('fsubmit', name)">
            <h1 class="text-center font-semibold text-xl">Event Validation</h1>
            <label for="name">Name:</label>
            <input type="text" id="name" v-model="name">
            <button type="subnit">Submit</button>

        </form>

    </div>



    <!-- V model Argument -->
    <form action="">
        
    </form>
</template>