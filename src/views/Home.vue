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
    const posts = ref([
      {title: 'some title', body: 'lsdfdsf dfd dfd dfddfddfddfd dfddfd dfd dfd dfd dfd dfd dfd dfd dfddfddfddfddfddfddfddfddfddfddfddfddfddfddfddfddfddfddfddfddfddfd dfd dfddfddfddfddfddfddfddfddfddfddfddfddfddfd dfddfddfddfddfddfddfddfddfddfddfddfddfddfddfddfddfddfddfd', id: 1},
      {title: 'another title', body: 'fdffdsfdsdsfs', id: 2},
    ])

    return {posts}
  }
}
</script>

<style>

</style>