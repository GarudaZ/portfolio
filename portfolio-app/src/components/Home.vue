<template>
	<div class="container">

		<div class="welcome">
			<p>Hi</p>
			<p>
				I'm

				<span style="font-weight: 800">Gareth Austin</span>
			</p>
			<RotatingWords />
		</div>
		<article>
			<p>
				Having discovered I had a taste for software development in my last
				role, I completed automation projects using Google Apps Script that
				saved the charity hours of work each week. The creativity involved in
				imagining improvements, and the problem solving and the learning needed
				to implement them really motivated my move to the tech sector. I have
				just completed a software development course with Northcoders and I am
				looking for my first junior development role.
			</p>
			<p>
				An experienced public speaker with a love of the English Language, I
				have a masters in English Literature and, as an ordained Buddhist, I
				teach meditation and Buddhism at my local centre.
			</p>
			<p>
				I love learning new technology and you can take a look at what I've been
				<a href="#/projects">working on here.</a> You can see
				<a class="other-link" href="#/about"
					>more about me and my skills here.</a
				>I'm open for work so feel free to get in touch.
			</p>
		</article>
		<aside>
			<div style="font-size: 18pt">
				<h2 style="color: rgba(255, 255, 255, 0.87)">Get in touch:</h2>
				<li>
					<a href="https://www.linkedin.com/in/gareth-austin-1bb12b301/"
						>Linkedin
					</a>
				</li>
				<li>
					<a href="https://github.com/GarudaZ">GitHub</a>
				</li>
				<li>
					<a href="mailto: garethjaustin@gmail.com">garethjaustin@gmail.com </a>
				</li>
			</div>
		</aside>
	</div>
</template>

<script>
import RotatingWords from "./WordRotator.vue";

export default {
	name: "App",
	components: {
		RotatingWords,
	},
};
</script>

<style scoped>
.welcome {
	font-size: 38px;
}
</style>
