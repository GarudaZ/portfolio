<script setup>
import { ref } from "vue";

const parentMessage = ref("Parent");
const projects = ref([
	{
		name: "Portfolio",
		screenshot: "portfolio-screenshot.png",
		desc: "This portfolio",
		github: "https://github.com/GarudaZ/portfolio",
		hosted: "You're here now!",
		wip: true,
		tech: ["Vue","CSS","Vite", "Typescript"]
	},
	{
		name: "Tetriplan",
		screenshot: "tetriplan-screenshot.png",
		desc: "A time blocking app made using Angular and MondoDB",
		github: "https://github.com/GarudaZ/tetriplan-frontend",
		hosted: "https://tetriplan.netlify.app",
		wip: false,
		tech: ["Angular", "mongoDB", "Firebase"]
	},
	{
		name: "NC News",
		screenshot: "ncnews-screenshot.png",
		desc: "A news web app with the ability to vote and comment on articles.",
		github: "https://github.com/GarudaZ/fe-nc-news",
		beGithub: "https://github.com/GarudaZ/nc-news",
		hosted: "https://ncnewsnow.netlify.app/",
		wip:false,
		tech: ["React", "Express", "HTML", "CSS", "Javascript"]
	},
]);
</script>

<template>
	
	<h1>Projects</h1>
	<div class="container">
		<div class="overview">

			<p>Here are my coding projects, past and present. You can also see what technology and skills were involved in each of them.</p>
		</div>
	<div class="cards-container">

		<li v-for="project in projects" class="card">
				<div class="card-header">
					<h2>{{ project.name }}</h2>
					<div v-if="project.wip" class="tag" style="background-color: #8BE9FD;">
						<p >IN PROGRESS</p>
					</div>
				</div>
			<a target="_blank" :href="project.hosted">
				<img :src="project.screenshot" alt="Screenshot of the project" />
			</a>
			<div class="tech-tags">
				<div v-for="tech in project.tech" class="tag">
					<p>{{ tech }}</p>
				</div>
			</div>
			<p>{{ project.desc }}</p>
			<li style="padding: 0;">
				<p>GitHub: <a :href="project.github"> {{ project.github }}</a>
				</p>
			</li>
			<li>
				<p>Hosted: <a :href="project.hosted"> {{ project.hosted }}</a>
				</p>
			</li>
		</li>
</div>
</div>
</template>
