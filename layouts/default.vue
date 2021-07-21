<template>
  <div class="content-wrapper">
    <header>
      <h1>The Diary of Manier</h1>
      <nav>
        <ul>
          <li>Home</li>
          <li>Blog</li>
          <li>About</li>
        </ul>
      </nav>
    </header>
    <main>
      <Nuxt />
    </main>
  </div>
</template>

<style>
.content-wrapper {
  max-width: 800px;
  margin: auto;
}
header {
  color: #eaf2ef;
  background-color: var(--rich-black-100);
  display: flex;
  align-items: center;
  padding: 1rem;
}

header nav {
  margin-left: auto;
}

nav ul {
  list-style: none;
  display: flex;
  gap: 2em;
}

main {
  color: var(--rich-black-100);
  background-color: var(--mint-cream-10);
}

.margin-auto {
  margin: auto;
}
</style>
