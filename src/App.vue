<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <nav>
      <RouterLink to="/todo">TodoList</RouterLink>
      <RouterLink to="/">Home</RouterLink>
    </nav>
  </header>
  <main>
    <RouterView />
  </main>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
}

header {
  height: 70px;
  line-height: 70px;
  background-color: #b8d7f3;
}

main {
  width: 85%;
  margin: 10px auto;
  padding: 10px;
  border: 1px solid #ccc;
  min-height: 70vh;
  border-radius: 4px;
}

nav {
  width: 100%;
  font-size: 14px;
  text-align: center;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  font-size: 20px;
  text-decoration: none;
  color: #fff;
}

nav a.router-link-exact-active {
  color: #1ea6e6;
}
</style>
