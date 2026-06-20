<script setup>
import { onMounted, ref } from 'vue';

// component state, when component is clicked
const selected = ref(false);

const props = defineProps({
  username: String,
  userId: String,
  avatarSrc: String,
  post: String
});

onMounted(() => {
  debugger;
  console.info(props.username);
  console.log('Component mounted with props:', props);
});
</script>

<template>
  <div
    class="cursor-pointer"
    :class="{ 'bg-[#faf9f5] border border-[pink]': selected }"
    @click="selected = !selected"
  >
    <div class="flex items-center mb-2">
      <img class="rounded-full mr-3" :src="props.avatarSrc" />
      <div class="font-bold mr-2 text-white">{{ props.username }}</div>
      <div>@{{ userId }}</div>
    </div>
    <div>{{ props.post }}</div>
  </div>
</template>
