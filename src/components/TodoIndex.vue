<template>
    {{  todos }}
</template>

<script>
// import { ref } from 'vue'

export default {
  async setup() {
    const todos = await fetch('https://jsonplaceholder.typicode.com/todos')
      .then(response => response.json())

    return {
        todos
    }
  }

}
</script>

<style lang="css" scoped>
</style>
