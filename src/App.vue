<template>
  <section class="container">
    <h2>{{ userName }}</h2>
    <h3>{{ userAge }}</h3>
    <!-- <h2>{{ user }}</h2> -->
    <button @click="changeAge">Change Age</button>
    <div>
      <input type="text" placeholder="First Name" @input="setFirstName" />
      <input type="text" placeholder="Last Name" @input="setLastName" />
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue';
// import { reactive } from 'vue';

const userAge = ref(22);
const firstName = ref('');
const lastName = ref('');

// Reactive only works with Objects
// An object is a must have
// const user = reactive({
//   name: 'Robin',
//   age: 22,
// });

const changeAge = () => {
  userAge.value++;
};

function setFirstName(event) {
  firstName.value = event.target.value;
}

function setLastName(event) {
  lastName.value = event.target.value;
}

const userName = computed(function () {
  return firstName.value + ' ' + lastName.value;
});

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
