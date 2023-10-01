<template>
  <div class="home">
    <input type="text" v-model="search">
    <div v-for="name in matchingNames" :key="name">
      {{ name }}
    </div>
  </div>
</template>

<script>
import { ref, reactive, computed, watch, watchEffect } from 'vue';


export default {
  name: 'Home',
  setup(){
    const search = ref('')
    const names = ref(['mario', 'luigi','yoshi','peach'])

    const stopWatch = watch(search, () => {
      console.log('watch func run')
    })

    const stopEffect = watchEffect(() => {
      console.log('watchEffect func run', search.value)
    })

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
    })

    const handleClick = () => {
      stopWatch()
      stopEffect()
    }

    return {names, search, matchingNames, handleClick}
  }
  
}
</script>
