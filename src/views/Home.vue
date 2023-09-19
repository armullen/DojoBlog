<template>
  <div class="home">
    <p>home</p>
    <p ref="p">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click me</button>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'Home',
  setup() {
    console.log('setup')

    const p = ref(null)
    console.log(p, p.value)

    let name = 'Mario'
    let age = 25

    const handleClick = () => {
      console.log(p, p.value)
      p.value.classList.add('test')
      p.value.textContent = 'hello, ninjas'
    }

    return {
      name: name,
      age: age,
      handleClick,
      p
    }
  },
}

</script>
