<template >
    
    <div class="text-center my-4">
        <h1 class="font-bold">Iterating over an Array:</h1>
      <ul>
        <li v-for="(item, index) in items" :key="index">
          {{ item }}
        </li>
      </ul>
    </div>





    
    <div class="text-center my-4">
        <h1 class="font-bold">Iterating over an Object:</h1>
      <ul>
        <li v-for="(value, key, index) in user" :key="key">
          {{ index }} {{ key }}: {{ value }}
        </li>
      </ul>
    </div>




    <div class="my-4 text-center">
    <ul>
        <h1 class="font-bold">Iterating with v-for and nested arrays</h1>
      <li v-for="group in groups" :key="group.id">
        <h3>{{ group.name }}</h3>
        <ul>
          <li v-for="item in group.items" :key="item.id">
            {{ item.name }}
          </li>
        </ul>
      </li>
    </ul>
  </div>





  <div class="my-4 text-center">
    <ul>
        <h1 class="font-bold">Iterating with v-for and Objects of Objects</h1>
      <li v-for="(user, key) in users" :key="key">
        <h3>{{ key }}</h3>
        <ul>
          <li v-for="(value, prop) in user" :key="prop">
            {{ prop }}: {{ value }}
          </li>
        </ul>
      </li>
    </ul>
  </div>




  <div class="my-4 text-center">
    <h1 class="font-bold">Iterating in range</h1>
    <ul>
        
      <li v-for="number in 4" :key="number">
        {{ number }}
      </li>
      <li v-for="number in 4" :key="number">
        <h1>Hello world</h1>
      </li>
    </ul>
  </div>



  <div class="my-4 text-center">
    <h1 class="font-bold">v-for with function</h1>
    <ul>
      <li v-for="item in generateItems()" :key="item">
        {{ item }}
      </li>
    </ul>
  </div>

  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const items = ref(['Apple', 'Banana', 'Orange']);



  const user = ref({
    name: 'John Doe',
    age: 25,
    email: 'johndoe@example.com'
  });



  
const groups = ref([
  {
    id: 1,
    name: 'Group A',
    items: [
      { id: 1, name: 'Item 1' },
      { id: 2, name: 'Item 2' },
    ]
  },
  {
    id: 2,
    name: 'Group B',
    items: [
      { id: 3, name: 'Item 3' },
      { id: 4, name: 'Item 4' },
    ]
  }
]);


const users = ref({
  user1: {
    name: 'John Doe',
    age: 25,
    email: 'johndoe@example.com'
  },
  user2: {
    name: 'Jane Smith',
    age: 30,
    email: 'janesmith@example.com'
  },
  user3: {
    name: 'Bob Johnson',
    age: 35,
    email: 'bobjohnson@example.com'
  }


});


function generateItems() {
  return ['Apple', 'Banana', 'Orange'];
}

  </script>




  
  