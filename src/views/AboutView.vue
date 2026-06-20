<template>
  <div class="lg:min-h-screen lg:flex lg:items-center">
    <h1>This is an about page </h1>
    <p>Count: <b>{{ count }}</b></p>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const count = ref(0);
const message = ref('Hello, Vue 3!');

onMounted(() => {
  console.log('Component has been mounted!');
  debugger;
  if (count.value < 2) {
    count.value++;
  }
});
</script>
