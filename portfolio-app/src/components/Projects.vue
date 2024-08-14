<script setup>
import { ref } from "vue";

const parentMessage = ref("Parent");
const projects = ref([
	{
		name: "Infinite Library Backend",
		desc: "The backend for my virtual book shelf app, an express server with a mongodb database, with a connection to the Open Library api. I explored using superagent instead of axios (which I've used before) for server requests. I also used faker for the first time to generate random isbn numbers for testing purposes.",
		wip: true,
		github: "https://github.com/GarudaZ/infinite-library-be",
		tech: ["express.js", "faker", "superagent", "mongoDB"],
	},
	{
		name: "ReView",
		desc: "A day review app that adds functionality to google tasks. I'm building it for my own use and as a chance to try out another framework. I'm still in the spiking phase.",
		wip: true,
	},
	{
		name: "Portfolio",
		screenshot: "portfolio-screenshot.png",
		desc: "The portfolio you're looking at now was built with Vue and makes use of the Dracula theme. It's hosted on Github pages, so it's very closely connected to my Github account.",
		github: "https://github.com/GarudaZ/portfolio",
		hosted: "You're here now!",
		wip: false,
		tech: ["Vue", "CSS", "Vite", "Typescript"],
	},
	{
		name: "Tetriplan",
		screenshot: "tetriplan-screenshot.png",
		desc: "A time blocking app made using Angular and MongoDB. Login is handled using Firebase to provide seamless integration with google and email accounts. This was created as a team project during my course at Northcoders",
		github: "https://github.com/GarudaZ/tetriplan-frontend",
		hosted: "https://tetriplan.netlify.app",
		wip: false,
		tech: ["Angular", "mongoDB", "Firebase"],
	},
	{
		name: "NC News",
		screenshot: "ncnews-screenshot.png",
		desc: "A news web app with the ability to vote and comment on articles, inspired by Reddit and produced during my time on the Northcoders course.",
		github: "https://github.com/GarudaZ/fe-nc-news",
		beGithub: "https://github.com/GarudaZ/nc-news",
		hosted: "https://ncnewsnow.netlify.app/",
		wip: false,
		tech: ["React", "Express", "Javascript"],
	},
]);
</script>

<template>
	<h1>Projects</h1>
	<div class="container">
		<div class="overview">
			<p>
				Here are my coding projects, past and present. You can also see what
				technology and skills were involved in making each of them.
			</p>
		</div>
		<ul class="cards-container">
			<li v-for="project in projects" :key="project.name" class="card">
				<div class="card-header">
					<a target="_blank" :href="project.hosted">
						<h2>{{ project.name }}</h2>
					</a>
					<div class="card-header-right">
						<div
							v-if="project.wip"
							class="tag"
							style="background-color: #8be9fd"
						>
							<p>WIP</p>
						</div>
						<a v-if="project.github" target="_blank" :href="project.github">
							<img
								style="width: 10vw; max-width: 40px; margin-left: 1em"
								src="/github-logo.png"
								alt="github logo"
							/>
						</a>
					</div>
				</div>
				<a v-if="project.screenshot" target="_blank" :href="project.hosted">
					<img :src="project.screenshot" alt="Screenshot of the project" />
				</a>
				<div class="tech-tags">
					<div v-for="tech in project.tech" :key="tech" class="tag">
						<p>{{ tech }}</p>
					</div>
				</div>
				<p>{{ project.desc }}</p>
				<div v-if="project.github" style="padding: 0">
					<p>
						GitHub: <a :href="project.github">{{ project.github }}</a>
					</p>
				</div>
				<div v-if="project.beGithub" style="padding: 0">
					<p>
						Backend GitHub:
						<a :href="project.beGithub">{{ project.beGithub }}</a>
					</p>
				</div>
				<div v-if="project.hosted">
					<p>
						Hosted: <a :href="project.hosted">{{ project.hosted }}</a>
					</p>
				</div>
			</li>
		</ul>
	</div>
</template>
