<template>
  <h1>home</h1>
  <PostList :posts="posts"/>
</template>

<script>

import PostList from '@/components/PostList.vue'
import getPosts from '../assets/composables/getPosts'
export default {
  name : 'Home',
  components: {PostList},
  setup(){
    const {posts, error, load} = getPosts()
    load()
    return {posts, error}
  }
}
</script>

<style>

</style>