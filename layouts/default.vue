<template>
  <div>
    <header>
      <h1>The Diary of Manier</h1>
      <nav>
        <ul>
          <li>
            <book-svg
              v-if="isViewingPath()"
              style="fill: white; height: 1em"
              class="icon"
            /><nuxt-link to="/"><span>Home</span></nuxt-link>
          </li>
          <li>
            <book-svg
              v-if="isViewingPath('/blog')"
              style="fill: white; height: 1em"
              class="icon"
            /><nuxt-link to="/blog"><span>Blog</span></nuxt-link>
          </li>
          <li>
            <book-svg
              v-if="isViewingPath('/about')"
              style="fill: white; height: 1em"
              class="icon"
            /><nuxt-link to="/about"><span>About</span></nuxt-link>
          </li>
        </ul>
      </nav>
    </header>
    <main>
      <Nuxt />
    </main>
  </div>
</template>

<script>
import BookSvg from '@/assets/icons/book.svg'
export default {
  components: {
    BookSvg,
  },
  methods: {
    isViewingPath(path = '/') {
      return this.$route.path === path
    },
  },
}
</script>

<style>
header {
  color: #eaf2ef;
  background-color: var(--rich-black-100);
  display: flex;
  align-items: center;
  padding: 1rem;
}

.sticky {
  position: fixed;
  top: 0;
  width: 100%;
}

header nav {
  margin-left: auto;
}

nav ul {
  list-style: none;
  display: flex;
  gap: 2.5em;
}

nav ul li {
  position: relative;
}

nav ul li .icon {
  fill: var(--mint-cream-10);
  height: 1em;
  position: absolute;
  left: -1.4rem;
  top: 1px;
}

nav ul li a {
  color: var(--mint-cream-10);
  text-decoration: none;
}

main {
  color: var(--rich-black-100);
  background-color: var(--mint-cream-10);
  max-width: 800px;
  margin: auto;
  padding: 1rem;
}

main h2 {
  color: #521945;
}

.margin-auto {
  margin: auto;
}
</style>
