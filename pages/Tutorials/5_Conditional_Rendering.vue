<template>
    <div class="text-center">
      <p v-if="showMessage">This message is being shown conditionally.</p>
      <button class="px-2 py-1  rounded " :class="[showMessage ? 'bg-red-300':'bg-green-200']" @click="toggleMessage">
        {{showMessage?"close":"open"}}
    </button>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const showMessage = ref(true);
  
  function toggleMessage() {
    showMessage.value = !showMessage.value;
  }
  </script>

  <!-- <template>
    <div>
      <p v-if="showMessage">This message is being shown conditionally with v-if.</p>
      <p v-else-if="showAlternateMessage">This message is being shown conditionally with v-else-if.</p>
      <p v-else>This message is being shown when none of the conditions are met.</p>
      <p v-show="showMessage">This message is being shown conditionally with v-show.</p>
  
      <button @click="toggleMessages">Toggle Messages</button>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const showMessage = ref(true);
  const showAlternateMessage = ref(false);
  
  function toggleMessages() {
    showMessage.value = !showMessage.value;
    showAlternateMessage.value = !showAlternateMessage.value;
  }
  </script>
 
  
  
  
  
  
   -->