<template>
  <div class="home">
    <p ref="p">My name is {{ name  }} and my age is {{ age }}</p>
    <button @click="handleClick">you clicked me</button>
    <button @click="age++">add 1 to age</button>
    <input type="text" v-model="name">
  </div>
</template>

<script>
import { ref, reactive } from 'vue';


export default {
  name: 'Home',
  setup(){

    let name = ref('mario');
    let age = ref(30)

    const handleClick = () => {
      name.value = 'luigi'
      age.value = '35'
    }

    return {name, age, handleClick, p}
  }
  
}
</script>
