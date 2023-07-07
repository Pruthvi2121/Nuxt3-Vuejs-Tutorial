<script setup>
const count = ref(0);
const name = ref("");
function IncreaseBy11(n){
    return count.value+=n;
}

// Declaring Emitted event
const emit = defineEmits(["increaseCount"])


// Event Validation
const handleSubmit = (name)=>{
    alert("form submited ")
    console.log("form submited ", name)
}
</script>

<template>
    <div>
        <h1 >Count : {{ count }}</h1>
        <!-- <Event @increaseCount="count++" /> -->
        <!-- <Event @increaseCount="(n)=>count+=n"/> -->
         <!-- <Event @increaseCount="IncreaseBy11" /> -->
        <Event  @fsubmit="handleSubmit"/>

        <hr>
        <div>
            <!-- <FormInput v-model="name" label="name"/>
            <FormInput v-model="name" label="contact"/> -->
            <FormInput2 v-model="name" label="contact"/>
        </div>
    </div>
</template>