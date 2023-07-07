<script setup>
    // const props = defineProps({
    //     name:String,
    //     age:Number
    // })

    // const props = defineProps({
    //     name:{
    //         type:String,
    //         required:true,
    //         default:"Pruthviraj",
    //         required:true,
    //     },
    //     age:{
    //         type:Number,
    //         default:21,
    //     },
    //     skill:Array
    // })

    // custom validation
     const prop = defineProps({
        name:{
            type:String,
            validator(propValue){
                return["Sonam", "Rahul","Vishwas"].includes(propValue)
            }
        },
        age:{
            type:Number,
            validator:(propValue)=> propValue > 0,
        }
     })
</script>

<template>
    <div class="text-center">
        <h1> My name {{ name }}</h1>
        <h1> I am {{ age }} year's old</h1>
        <h1>I have - {{ skill }}</h1>
    </div>
</template>