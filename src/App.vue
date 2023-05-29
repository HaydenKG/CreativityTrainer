<script setup lang="ts">
import { RouterLink, RouterView, useRoute } from 'vue-router'

const route = useRoute();

</script>

<template>
  <nav>
    <h2>Creativity Trainer</h2>
    <div id="routerElements">
      <RouterLink to="/" :disabled="route.path === '/'">Home</RouterLink>
      <RouterLink to="/about" :disabled="route.path === '/about'">About</RouterLink>
    </div>
  </nav>

  <RouterView />
</template>

<style scoped>
nav {
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  justify-items: start;
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin: 1.4rem 0;
}

nav a.router-link-exact-active {
  color: var(--color-text);
  text-decoration: underline;
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
  font-size: 1.4rem;
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 620px) {
  #routerElements {
    position: absolute;
    justify-self: center;
  }
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
