<template>
  <SocialPost
    v-for="(post, index) in posts"
    :username="post.username"
    :userId="post.userId"
    :avatarSrc="post.avatar"
    :post="post.post"
    :comments="post.comments"
    :likes="post.likes"
    :retweets="post.retweets"
    :key="post.userId"
    @delete-post="onDeletePost"
  ></SocialPost>
  <!-- @delete-post="onDeletePost(index)" -->
</template>
  
  <script setup>
  import { reactive } from 'vue';
  import SocialPost from '../molecules/SocialPost.vue'
  
  const posts = reactive([
    { username: "Username one",
      userId: "usernameId1",
      avatar: "https://i.pravatar.cc/40",
      post: "This is my post",
      comments: [
        "great post",
        "amazing post"
      ],
      likes: 2,
      retweets: 1,
      tags: [
        "tag 1"
      ]
    },
    { username: "Username two",
      userId: "usernameId2",
      avatar: "https://i.pravatar.cc/41",
      post: "This is my second post",
      comments: [],
      likes: 3,
      retweets: 1,
      tags: [
        "tag 1",
        "tag 2"
      ]
    },
    { username: "Username three",
      userId: "usernameId3",
      avatar: "https://i.pravatar.cc/42",
      post: "This is my third post",
      comments: [
        "cool post",
        "I disagree!"
      ],
      likes: 3,
      retweets: 2,
      tags: [
        "tag 3",
        "tag 4"
      ]
    },
    { username: "Username four",
      userId: "usernameId4",
      avatar: "https://i.pravatar.cc/43",
      post: "This is my fourth post",
      comments: [],
      likes: 2,
      retweets: 0,
      tags: [
        "tag 5"
      ]
    }
  ]);

  // Delete post using the user Id argument, emited by the event in the child component. 
  // This is the preferred way to delete a post, as it does not rely on the index of the post in the array (which may change if posts are added or removed)
  const onDeletePost = (userId) => { 
    debugger;
    console.log('In SocialPosts.vue (parent). Deleting post ', userId);
    const postIndex = posts.findIndex(post => post.userId === userId);

    // Check if post exists, before attempting to delete it. If not, log a warning and return early.
    if (postIndex == -1) {
      console.warn(`Post with userId "${userId}" was not found.`)
      return;
    }

    // Post exists
    const post = posts[postIndex];
    console.log('Deleting post ', post.userId, " with contentL ", post.post);
    posts.splice(postIndex, 1);
  }

  // const onDeletePost = (postIndex) => { 
  //   // Alternate way of deleting post, via the index exposed within the v-for (and added to the event declaration in the template)
  //   posts.splice(postIndex, 1);
  // }
  </script>
  