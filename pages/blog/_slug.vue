<template>
  <article>
    <div class="post-header-wrapper">
      <h1>{{ post.title }}</h1>
      <div class="author-block">
        <img width="80" :src="post.author.img" :alt="post.author.alt" />
        <div>
          <h3>Posted by {{ post.author.name }}</h3>
          <h4>Last updated: {{ formatDate(post.updatedAt) }}</h4>
        </div>
      </div>
    </div>
    <nuxt-content class="content" :document="post" />
    <pre> {{ post }} </pre>
  </article>
</template>

<script>
export default {
  asyncData: async function ({ $content, params }) {
    const post = await $content('posts', params.slug).fetch()
    return { post }
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
h1 {
  line-height: 1.5;
}
h2,
p {
  margin-bottom: 1em;
  line-height: 1.5;
}

.post-header-wrapper {
  margin: 1em;
}

.author-block {
  display: flex;
  align-items: center;
  margin-bottom: 1em;
}

.author-block > * {
  padding: 0 0.5rem;
}

.content {
  padding: 1rem;
  border: 1px solid #8fd5a6;
  border-radius: 10px;
  margin: 0.5em;
}
</style>
