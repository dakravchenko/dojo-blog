<template>
  <h1>home</h1>
  <PostList :posts="posts"/>
</template>

<script>

import {ref} from 'vue'
import PostList from '@/components/PostList.vue'
export default {
  name : 'Home',
  components: {PostList},
  setup(){
    const posts = ref([])
    const error = ref(null)

    const load = async () => {
      try {
        let data = await fetch('http://localhost:3000/posts')
        if(!data.ok){
          throw Error('no data available')
        }
        posts.value = await data.json()

      } catch (error) {
        error.value = error.message
      }
    }
    load()
    return {posts, error}
  }
}
</script>

<style>

</style>