<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <header class="leading-[1.5] max-h-screen lg:flex lg:items-center lg:pr-20">
    <img
      alt="Vue logo"
      class="block mx-auto mb-8 lg:mx-0 lg:mr-8 lg:mb-0"
      src="@/assets/logo.svg"
      width="125"
      height="125"
    />

    <div class="lg:flex lg:items-start lg:flex-wrap">
      <HelloWorld msg="You did it!" />

      <nav class="w-full text-xs text-center mt-8 lg:text-left lg:-ml-4 lg:text-base lg:py-4 lg:mt-4">
        <RouterLink
          to="/"
          class="inline-block px-4 border-l border-[var(--color-border)] first:border-0 [&.router-link-exact-active]:text-[var(--color-text)] [&.router-link-exact-active]:hover:bg-transparent"
        >Home</RouterLink>
        <RouterLink
          to="/about"
          class="inline-block px-4 border-l border-[var(--color-border)] first:border-0 [&.router-link-exact-active]:text-[var(--color-text)] [&.router-link-exact-active]:hover:bg-transparent"
        >About</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>
