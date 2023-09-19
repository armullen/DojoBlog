<!-- <template>
  <div class="home">
    <h1>Home</h1>
    <h2>Refs</h2>
    <p>{{  ninjaOne.name }} - {{ ninjaOne.age }}</p>
    <button @click="updateNinjaOne">Update Ninja One</button>
    <h2>Reactive</h2>
    <p>{{  ninjaTwo.name }} - {{ ninjaTwo.age }}</p>
    <button @click="updateNinjaTwo">Update Ninja Two</button>
  </div>
</template>

<script>
import { ref, reactive } from 'vue'

export default {
  name: 'Home',
  setup() {
    const ninjaOne = ref({ name: 'Mario', age: 25 })
    const ninjaTwo = reactive({ name: 'Luigi', age: 35}) 

    const updateNinjaOne = () => {
      ninjaOne.value.age = 30
    }

    const updateNinjaTwo = () => {
      ninjaTwo.age = 45
    }

    return {
      ninjaOne, updateNinjaOne, ninjaTwo, updateNinjaTwo
    }
  },
}

</script> -->


<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search">
    <p>search term - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
  </div>
</template>

<script>
import { computed, ref } from 'vue'

export default {
  name: 'Home',
  setup() {
    const search = ref('')
    const names = ref(['Mario', 'Luigi', 'Yoshi', 'Koopa', 'Peach', 'Bowser', 'Toad'])

    const matchingNames = computed(() => {
      return names.value.filter((name) => {
        return name.toLowerCase().includes(search.value.toLowerCase())
      })
    })

    return {
       names,
       search,
       matchingNames 
    }
  }
}
</script>