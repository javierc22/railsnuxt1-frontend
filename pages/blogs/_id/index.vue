<template lang="html">
  <div>
    <div v-if="blog">
      <h1>
        {{ blog.title }}
      </h1>
      <p>{{ blog.body }}</p>
    </div>
  </div>
</template>

<script>
import * as BlogsApi from '@/utils/blogsApi'
export default {
  data() {
    return {
      blog: null
    }
  },
  async mounted() {
    console.log('THIS.$ROUTE.PARAMS.ID', this.$route.params.id)
    const response = await BlogsApi.show(this.$route.params.id)
    console.log('RESPONSE', response)
    this.blog = response.data
  },
  methods: {
    async handleDestroyClicked() {
      // const response = await BlogsApi.destroy(this.$route.params.id)
      const response = await BlogsApi.destroy(this.blog.id)
      console.log('RESPONSE', response)
      this.$router.replace({ name: 'blogs' })
    }
  }
}
</script>