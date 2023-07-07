<script>
const isActive = ref(true);
const isImportant = ref(false);

const classObj = reactive({
    active:true,
    'f-bold':true,
    itext:true  
})

// computed property

const myClass = computed(()=>({
    active : isActive.value,
    "f-bold": isImportant.value
}))


// Binding to array
const current = ref("bg-red-300")
const error = ref("error")
</script> 


<template>
    <h1 class="text-red">Hello 1</h1>
    <h1 class="text-red f-bold">Hello 2</h1>
    <!-- Binding objects -->
    <h1  v-bind:class="{'active':isActive}">Hello 3</h1>
    <h1  :class="{'active':isActive}">Hello 4</h1>
    <h1 class="text-red" :class="{'active':isActive}">Hello 5</h1>
    <h1 :class="{'active':isActive, 'f-bold':isImportant}">Hello 6</h1>
    <h1 :class="classObj">Hello 7</h1>
    <h1 :class="myClass">Hello 8</h1>

    <!-- Binding to array -->
    <h1 :class="[current, error]">Hello 9</h1>
    <h1 :class="[isActive ? current : '', error]">Hello 10</h1>

    
</template> 


<style>
.current{
    font-weight: bold;
    color: blueviolet;
    font-size: 20px;
}
.bg-red{
    background: rgba(193, 37, 37, 0.486);
}
</style>