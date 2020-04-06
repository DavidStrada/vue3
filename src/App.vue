<template>
  <h1>Hello Vue 3!</h1>
  <Suspense>
    <template #default>
      <h3>Todos</h3>
      <todo-index />
      <hr>
      <h3>Posts</h3>
      <posts />
      <hr>
      <h3>Users</h3>
      <users />
    </template>
    <template #fallback>
      <div>Loading...</div>
    </template>
  </Suspense>
  <hr>
  <!-- <button @click="inc">Clicked {{ count }} times.</button> -->
</template>

<script>
import { ref, onErrorCaptured } from 'vue'
import TodoIndex from './components/TodoIndex.vue'
import Posts from './components/Posts.vue'
import Users from './components/Users.vue'

export default {
  components: {
    TodoIndex,
    Posts,
    Users
  },
  setup() {
    const count = ref(0)
    const inc = () => {
      count.value++
    }

    onErrorCaptured(e => console.error('error ==> ',e))

    return {
      count,
      inc
    }
  }
}
</script>

<style scoped>
img {
  width: 200px;
}
h1 {
  font-family: Arial, Helvetica, sans-serif;
}
</style>
