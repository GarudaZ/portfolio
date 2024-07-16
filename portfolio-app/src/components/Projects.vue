<script setup>
import { ref } from "vue";

const parentMessage = ref("Parent");
const projects = ref([
	{
		name: "Portfolio",
		screenshot: "test",
		desc: "This portfolio",
		github: "https://github.com/GarudaZ/portfolio",
	},
	{
		name: "Tetriplan",
		screenshot: "tetriplanscreenshot.png",
		desc: "A time blocking app made using Angular and MondoDB",
		github: "https://github.com/GarudaZ/tetriplan-frontend",
	},
	{
		name: "NC News",
		screenshot: "ncnewsscreenshot.png",
		desc: "A news web app with the ability to vote and comment on articles.",
		github: "https://github.com/GarudaZ/fe-nc-news",
		beGithub: "https://github.com/GarudaZ/nc-news",
	},
]);
</script>

<template>
	<h1>Projects</h1>
	<li v-for="project in projects" class="card">
		<h2>{{ project.name }}</h2>
		<img :src="project.screenshot" alt="Screenshot of the project" />
		<p>{{ project.desc }}</p>
		<a :href="project.github">{{ project.github }}</a>
	</li>
</template>
