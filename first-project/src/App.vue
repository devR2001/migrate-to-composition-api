<template>
  <section class="container">
    <h2>{{ userName }}</h2>
    <h3>{{ userAge }}</h3>
    <!-- <h2>{{ user }}</h2> -->
    <button @click="changeAge">Change Age</button>
    <div>
      <input type="text" placeholder="First Name" v-model="firstName" />
      <input type="text" placeholder="Last Name" ref="lastNameInput" />
      <button @click="setLastName">Set Last Name</button>
    </div>
    <UserData :userAge="userAge" :lastName="lastName" :firstName="firstName" />
  </section>
</template>

<script setup>
import UserData from './components/UserData.vue';
import {
  ref,
  computed,
  watch,
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
} from 'vue';
// import { reactive } from 'vue';

const userAge = ref(22);
const firstName = ref('');
const lastName = ref('');
const lastNameInput = ref(null);

// Reactive only works with Objects
// An object is a must have
// const user = reactive({
//   name: 'Robin',
//   age: 22,
// });

const changeAge = () => {
  userAge.value++;
};

// function setFirstName(event) {
//   firstName.value = event.target.value;
// }

function setLastName() {
  lastName.value = lastNameInput.value.value;
}

const userName = computed(function () {
  return firstName.value + ' ' + lastName.value;
});

watch([userAge, userName], function (newValues, oldValues) {
  console.log('old age:', oldValues[0]);
  console.log('new age:', newValues[0]);
  console.log('old name:', oldValues[1]);
  console.log('new name:', newValues[1]);
});

// watch(userAge, function (newValue, oldValue) {
//   console.log('old age:', oldValue);
//   console.log('new age:', newValue);
// });

// setTimeout(function () {
//   user.name = 'Haas';
//   user.age = 23;
// }, 2000);

////////////////////////////////////////////
//                Mount                   //
////////////////////////////////////////////

onBeforeMount(() => {
  console.log('onBeforeMount');
});

onMounted(() => {
  console.log('onMounted');
});

onBeforeUpdate(() => {
  console.log('onBeforeUpdate');
});

onUpdated(() => {
  console.log('onUpdated');
});

onBeforeUnmount(() => {
  console.log('onBeforeUnmount');
});

onUnmounted(() => {
  console.log('onUnmounted');
});
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
