<script setup>
import { ref } from "vue";

const parentMessage = ref("Parent");
const projects = ref([
	{
		name: "NC News",
		screenshot: "vite.svg",
		desc: "A news web app with the ability to vote and comment on articles.",
	},
	{
		name: "Tetriplan",
		screenshot: "vue.svg",
		desc: "A time blocking app",
	},
]);
</script>

<template>
	<h1>Projects</h1>
	<li v-for="project in projects" class="card">
		<h2>{{ project.name }}</h2>
		<img :src="project.screenshot" alt="Screenshot of the project" />
		<p>A news web app with the ability to vote and comment on articles.</p>
	</li>
</template>
