<script setup>

const props = defineProps({modelValue:String, label:String})
const emit = defineEmits(['update:modelValue'])
</script>


<template>
    <div class="flex flex-col mx-5">
        <label >{{ label }}</label>
        <input type="text" 
        :value="modelValue"
        @input="$emit('upddate:modelValue', $event.target.value)"
        class="bg-green-200  rounded focus:outline-none px-2"
        >
    </div>
</template>

