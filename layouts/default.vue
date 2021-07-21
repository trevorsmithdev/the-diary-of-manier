<template>
  <div>
    <header>
      <h1>The Diary of Manier</h1>
      <nav>
        <ul>
          <li><nuxt-link to="/">Home</nuxt-link></li>
          <li><nuxt-link to="/blog">Blog</nuxt-link></li>
          <li><nuxt-link to="/about">About</nuxt-link></li>
        </ul>
      </nav>
    </header>
    <main>
      <Nuxt />
    </main>
  </div>
</template>

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
  gap: 2em;
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
