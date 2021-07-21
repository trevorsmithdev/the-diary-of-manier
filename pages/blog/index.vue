<template>
  <div class="blog">
    <h2>Recent</h2>
    <div class="recent-posts-container">
      <div v-for="post in posts" :key="post.slug" class="post-preview">
        <h3>{{ post.title }}</h3>
        <h4>Updated: {{ formatDate(post.updatedAt) }}</h4>
        <p>{{ post.description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  asyncData: async function ({ $content }) {
    const posts = await $content('posts').fetch()
    return { posts }
  },
  methods: {
    formatDate: function (date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' }
      return new Date(date).toLocaleDateString('en', options)
    },
  },
}
</script>

<style>
.post-preview {
  margin-bottom: 2em;
  border-bottom: 1px solid #521945;
  padding: 0.5rem;
}

.recent-posts-container {
  margin-bottom: 1em;
}

.blog h2 {
  border-bottom: 2px solid #521945;
}
</style>
