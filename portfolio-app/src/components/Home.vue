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

		<article style="font-size: 16pt">
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
				teach meditation and Buddhism at my local centre. I'm open for work so
				feel free to get in touch.
			</p>
			<p>
				I love learning new technology and you can take a look at what I've been
				<a href="#/projects">working on here.</a>
			</p>
			<!-- <a [routerLink]="[ '/projects', routeParam ]">here</a> -->
			<!-- <a :to="{ path: '(/projects)' }">here</a> -->
		</article>
		<aside>
			<p style="font-size: 18pt">
				Get in touch:
				<a href="mailto: garethjaustin@gmail.com">garethjaustin@gmail.com </a>
			</p>
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
