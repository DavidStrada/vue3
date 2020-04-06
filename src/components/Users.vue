<template>
    {{ users }}
</template>

<script>
export default {
  async setup() {
    const users = await Promise.reject(new Error('fail'));

    return {
        users
    }
  }
}
</script>

<style lang="css" scoped>
</style>
