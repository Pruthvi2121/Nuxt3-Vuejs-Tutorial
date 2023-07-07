<script setup>

const props = defineProps({modelValue:String, label:String})
const emit = defineEmits(['update:modelValue'])
const value = computed({
    get(){
        return props.modelValue;
    },
    set(value){
        emit("update:modelValue", value);
    },
})
</script>


<template>
    <div class="flex flex-col mx-5">
        <label >{{ label }}</label>
        <input type="text" 
        
        class="bg-yellow-200  rounded focus:outline-none px-2"
        v-model="value"
        >
    </div>
</template>

