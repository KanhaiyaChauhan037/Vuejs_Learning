<script setup>
import { ref } from "vue";
const count = ref(0);

const inc = () => {
  count.value++;
};
const dec = () => {
  count.value--;
};
</script>

<template>
  <h1>Counter App</h1>

  <button @click="inc">Inc</button>
  <button @click="dec">Dec</button>
  <h4>{{ count }}</h4>
</template>
