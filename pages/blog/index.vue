<template>
  <div>
    <h3>Blog</h3>
    <div v-for="post in posts" :key="post.title">
      <h4>{{ post.title }}</h4>
      <p>{{ post.preview }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      posts: [{ title: 'Title', preview: 'lorem ipsum blah blah blah' }],
    }
  },
}
</script>

<style></style>
