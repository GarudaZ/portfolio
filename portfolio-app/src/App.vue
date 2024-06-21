<script setup>
import { ref, computed } from "vue";
import Home from "./components/Home.vue";
import About from "./components/About.vue";
import Projects from "./components/Projects.vue";
import NotFound from "./components/NotFound.vue";

const routes = {
	"/": Home,
	"/about": About,
	"/projects": Projects,
};

const currentPath = ref(window.location.hash);

window.addEventListener("hashchange", () => {
	currentPath.value = window.location.hash;
});

const currentView = computed(() => {
	return routes[currentPath.value.slice(1) || "/"] || NotFound;
});
</script>

<template>
	<a href="#/">Home</a> | <a href="#/about">About</a> |
	<a href="#/projects">Projects</a>
	<component :is="currentView" />
</template>

<style scoped>
.logo {
	height: 6em;
	padding: 1.5em;
	will-change: filter;
	transition: filter 300ms;
}
.logo:hover {
	filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
	filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
