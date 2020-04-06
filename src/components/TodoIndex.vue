<template>
    {{  todos }}
</template>

<script>
export default {
  async setup() {
    const todos = await fetch('https://jsonplaceholder.typicode.com/todos?_page=1&_limit=5')
      .then(response => response.json())

    return {
        todos
    }
  }
}
</script>

<style lang="css" scoped>
</style>
