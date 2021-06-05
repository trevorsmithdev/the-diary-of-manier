<template>
  <article>
    <p>Post last updated: {{ formatDate(post.updatedAt) }}</p>
    <nuxt-content :document="post" />
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
    // eslint-disable-next-line object-shorthand
    formatDate: function (date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' }
      return new Date(date).toLocaleDateString('en', options)
    },
  },
}
</script>

<style>
h1,
h2,
h3,
h4,
p {
  margin-bottom: 1em;
}
</style>
