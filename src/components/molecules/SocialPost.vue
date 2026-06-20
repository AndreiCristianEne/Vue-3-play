<script setup >
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
  class="SocialPost"
  :class="{ SocialPost__selected: selected }"
  @click = "selected = !selected"
  >
    <div class="header">
      <img class="avatar" :src="props.avatarSrc" />
      <div class="name">{{ props.username }}</div>
      <div class="userId">@{{ userId }}</div>
    </div>
    <div class="post">{{ props.post }}</div>
  </div>
</template>

<style lang="scss">
.SocialPost{
  &:hover {
    cursor: pointer;
  }
  
  &__selected {
    background-color: #faf9f5;
    border: pink solid 1px;
  }

  .header {
    display: flex;
    align-items: center;
    margin-bottom: 8px;;
  }
  .avatar {
    border-radius: 50%;
    margin-right: 12px;
  }
  .name {
    font-weight: bold;
    margin-right: 8px;
    color: white;
  }
}
</style>