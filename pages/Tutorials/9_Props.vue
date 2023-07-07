<script setup>
    const channel = ref("Code Evolution")
</script>

<template>
    <h1>Parent compoent</h1>
    <!-- static props -->
    <Greet name="Vishwas"/>
    <!-- Dynamic props -->
    <Greet :channel="channel"/>

    <!-- Prop Validation -->
     <!-- <PropValidation name="Harry" age="45"/> -->       <!--  give error  -->
     <PropValidation name="Harry" :age="45"/>   <!-- not give error give error  -->
     <PropValidation name="Mia" :skill="['python','java','c++','css']" />   <!-- not give error give error  -->
     
   
</template>
