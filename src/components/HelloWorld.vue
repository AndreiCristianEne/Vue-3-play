<script setup>
defineProps({
  msg: String,
})
</script>

<template>
  <div>
    <h1 class="green font-medium text-[2.6rem] relative -top-[10px] text-center lg:text-left">{{ msg }}</h1>
    <h3 class="text-[1.2rem] text-center lg:text-left">
      You've successfully created a project with
      <a href="https://vitejs.dev/" target="_blank" rel="noopener">Vite</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>.
    </h3>
  </div>
</template>
