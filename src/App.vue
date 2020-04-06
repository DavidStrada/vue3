<template>
  <h1>Hello Vue 3!</h1>
  <Suspense>
    <template #default>
      <todo-index />
    </template>
    <template #fallback>
      <div>Loading...</div>
    </template>
  </Suspense>
  <hr>
  <button @click="inc">Clicked {{ count }} times.</button>
</template>

<script>
import { ref } from 'vue'
import TodoIndex from './components/TodoIndex.vue'

export default {
  components: {
    TodoIndex
  },
  setup() {
    const count = ref(0)
    const inc = () => {
      count.value++
    }

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
