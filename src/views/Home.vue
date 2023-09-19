<!-- LESSON ONE -->

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

<!-- LESSSON TWO -->
<!-- <template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search">
    <p>search term - {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
    <button @click="handleClick">Stop Watching</button>
  </div>
</template>

<script>
import { computed, ref, watch, watchEffect } from 'vue'

export default {
  name: 'Home',
  setup() {
    const search = ref('')
    const names = ref(['Mario', 'Luigi', 'Yoshi', 'Koopa', 'Peach', 'Bowser', 'Toad'])

    const stopWatch = watch(search, () => {
      console.log('watch function run')
    })

    const stopWatchEffect = watchEffect(() => {
      console.log('watch effect run', search.value)
    })

    const matchingNames = computed(() => {
      return names.value.filter((name) => {
        return name.toLowerCase().includes(search.value.toLowerCase())
      })
    })

    const handleClick = () => {
      stopWatch()
      stopWatchEffect()
    }

    return {
      names,
      search,
      matchingNames,
      handleClick
    }
  }
}
</script> -->

<!-- LESSON THREE -->

<template>
  <div class="home">

    <h1>Home</h1>
    <PostList v-if="showPosts" :posts="posts" />
    <button @click="showPosts = !showPosts">toggle posts</button>
    <button @click="posts.pop()">remove post</button>
    
  </div>
</template>

<script>
import { ref } from 'vue'
import PostList from '@/components/PostList.vue'

export default {
  name: 'Home',
  components: {
    PostList
  },
  setup() {
    const posts = ref([
      { title: 'welcome to the blog', body: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.', id: 1},
      { title: 'vue 3 composition api', body: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.', id: 2},
      { title: 'the basics of javascript', body: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.', id: 3},
    ])

    const showPosts = ref(true)

    return {
      posts,
      showPosts 
    }
  }
}

</script>