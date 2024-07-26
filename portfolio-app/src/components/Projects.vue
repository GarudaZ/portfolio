<script setup>
import { ref } from "vue";

const parentMessage = ref("Parent");
const projects = ref([
	{
		name: "Portfolio",
		screenshot: "portfolio-screenshot.png",
		desc: "The portfolio you're looking at now was built with Vue and makes use of the Dracula theme. It's hosted on Github pages, so it's very closely connected to my Github account.",
		github: "https://github.com/GarudaZ/portfolio",
		hosted: "You're here now!",
		wip: true,
		tech: ["Vue", "CSS", "Vite", "Typescript"],
	},
	{
		name: "Tetriplan",
		screenshot: "tetriplan-screenshot.png",
		desc: "A time blocking app made using Angular and MongoDB. Login is handled using Firebase to provide seemless intregration with google and email accounts.",
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
				technology and skills were involved in each of them.
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
							<p>IN PROGRESS</p>
						</div>
						<a target="_blank" :href="project.github">
							<img
								style="width: 40px; margin-left: 1em"
								src="/github-logo.png"
								alt="github logo"
							/>
						</a>
					</div>
				</div>
				<a target="_blank" :href="project.hosted">
					<img :src="project.screenshot" alt="Screenshot of the project" />
				</a>
				<div class="tech-tags">
					<div v-for="tech in project.tech" :key="tech" class="tag">
						<p>{{ tech }}</p>
					</div>
				</div>
				<p>{{ project.desc }}</p>
				<div style="padding: 0">
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
				<div>
					<p>
						Hosted: <a :href="project.hosted">{{ project.hosted }}</a>
					</p>
				</div>
			</li>
		</ul>
	</div>
</template>
