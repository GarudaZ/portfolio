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
	<header>
		<a href="#/">Home</a> | <a href="#/about">About</a> |
		<a href="#/projects">Projects</a>
	</header>
	<main>
		<component :is="currentView" />
	</main>
</template>
