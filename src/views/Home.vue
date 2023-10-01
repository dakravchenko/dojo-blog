<template>
  <div class="home">
    <p>{{ ninjaOne.age }} -- {{ ninjaOne.name }}</p>
    <p>{{ ninjaTwo.age }} -- {{ ninjaTwo.name }}</p>
    <button @click="updateNinjaOne">Update ninja one</button>
    <button @click="updateNinjaTwo">Update ninja two</button>
  </div>
</template>

<script>
import { ref, reactive } from 'vue';


export default {
  name: 'Home',
  setup(){
    const ninjaOne = ref({name: 'mario', age: 30})
    const ninjaTwo = reactive({name: 'luigi', age: 35})

    const updateNinjaOne = () => {
      ninjaOne.value.age = 40
    }
    const updateNinjaTwo = () => {
      ninjaTwo.age = 45
    }

    return {ninjaOne, updateNinjaOne, ninjaTwo, updateNinjaTwo}
  }
  
}
</script>
