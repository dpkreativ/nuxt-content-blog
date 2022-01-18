<template>
  <Tutorial />
</template>

<script>
export default {
  async asyncData({ $content }) {
    const posts = await $content()
      .only(['title', 'image', 'tags', 'slug'])
      .sortBy(['createdAt', 'desc'])
      .fetch()

    console.log('posts', posts)

    return {
      posts,
    }
  },
}
</script>
