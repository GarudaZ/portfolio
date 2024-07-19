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

const currentPath = ref(window.location.pathname);

window.addEventListener("popstate", () => {
	currentPath.value = window.location.pathname;
});

const navigate = (path) => {
	window.history.pushState({}, path, path);
	currentPath.value = path;
};

const currentView = computed(() => {
	return routes[currentPath.value] || NotFound;
});

const applyHighlight = (path) => {
	return currentPath.value === path ? "highlight" : "";
};
</script>

<template>
	<header>
		<a :class="applyHighlight('/')" href="/">Home</a> |
		<a :class="applyHighlight('/about')" href="/about">About</a> |
		<a :class="applyHighlight('/projects')" href="/projects">Projects</a>
	</header>
	<main>
		<component :is="currentView" />
	</main>
	<footer>
		<p>Made by Gareth Austin 2024</p>
	</footer>
</template>
