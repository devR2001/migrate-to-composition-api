<template>
  <div>
    <!-- <h2>{{ props.userName }}</h2> -->
    <h2>{{ props.firstName }}</h2>
    <h2>{{ props.lastName }}</h2>
    <h2>{{ userDataComputed }}</h2>
    <h3>{{ props.userAge }}</h3>
  </div>
</template>

<script setup>
import { defineProps, computed } from 'vue';
const props = defineProps({
  firstName: String,
  lastName: String,
  userAge: Number,
});

const userDataComputed = computed(() => {
  return props.firstName + ' ' + props.lastName;
});
</script>

<style></style>
