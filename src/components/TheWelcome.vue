<script setup>
import { reactive, onMounted } from 'vue';
import SocialPost from './molecules/SocialPost.vue';

const posts = reactive([
  {
    username: 'Username one',
    userId: 'usernameID1',
    avatarSrc: 'https://i.pravatar.cc/40',
    post: 'This is my post'
  },
  {
    username: 'Username two',
    userId: 'usernameID2',
    avatarSrc: 'https://i.pravatar.cc/41',
    post: 'This is a nice post'
  }
]);

onMounted(() => {
  // debugger;
  console.log('TheWelcome component has been mounted!');
});
</script>

<template>
  <SocialPost
    v-for="(post, index) in posts"
    :key="index"
    :username="post.username"
    :userId="post.userId"
    :avatarSrc="post.avatarSrc"
    :post="post.post"
  />
</template>
