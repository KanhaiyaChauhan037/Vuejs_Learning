<!-- if we are use ref method for counter app then you need setup in <script setup></script> use this type  -->

<script >
// import { ref } from "vue";
// const count = ref(0);

// const inc = () => {
//   count.value++;
// };
// const dec = () => {
//   count.value--;
// };



export default {
  data() {
    return {
      count: 0,
    }
  },
  methods: {
    inc() {
      this.count++;
    },
dec() {
  this.count--;
}
  }
}


</script>

<template>
  <h1>Counter App</h1>

  <button @click="inc">Inc</button>
  <button @click="dec">Dec</button>
  <h4>{{ count }}</h4>
</template>
