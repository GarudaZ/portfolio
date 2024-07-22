<template>
  <header>
    <router-link :class="applyHighlight('/')" to="/">Home</router-link> |
    <router-link :class="applyHighlight('/about')" to="/about">About</router-link> |
    <router-link :class="applyHighlight('/projects')" to="/projects">Projects</router-link>
  </header>
  <main>
    <router-view></router-view>
  </main>
  <footer>
    <p>Made by Gareth Austin 2024</p>
  </footer>
</template>

<script setup>
import { useRoute } from 'vue-router';

const route = useRoute();

const applyHighlight = (path) => {
  return route.path === path ? 'highlight' : '';
};
</script>

<style>
.highlight {
  font-weight: bold;
}
</style>
