<template>
  <section class="container">
    <h2>{{ userName }}</h2>
    <h3>{{ userAge }}</h3>
    <!-- <h2>{{ user }}</h2> -->
    <button @click="changeAge">Change Age</button>
  </section>
</template>

<script setup>
import { ref } from 'vue';
// import { reactive } from 'vue';

const userName = ref('Robin');
const userAge = ref(22);

// Reactive only works with Objects
// An object is a must have
// const user = reactive({
//   name: 'Robin',
//   age: 22,
// });

const changeAge = () => {
  userAge.value++;
};

// setTimeout(function () {
//   user.name = 'Haas';
//   user.age = 23;
// }, 2000);
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

.container {
  margin: 3rem auto;
  max-width: 30rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
  text-align: center;
}
</style>
