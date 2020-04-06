<template>
    {{ posts }}
</template>

<script>
export default {
  async setup() {
    const posts = await fetch('https://jsonplaceholder.typicode.com/posts?_page=1&_limit=5')
      .then(response => response.json())

    return {
        posts
    }
  }
}
</script>

<style lang="css" scoped>
</style>
