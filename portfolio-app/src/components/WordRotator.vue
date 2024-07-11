<template>
	<div class="rotating-word">
		<p :style="{ color: currentColour }">{{ displayedWord }}</p>
	</div>
</template>

<script>
export default {
	data() {
		return {
			words: [
				"Software Developer",
				"Software Engineer",
				"Frontend Developer",
				"Backend Developer",
				"JavaScript Developer",
			],
			colours: ["#ff5555", "#8be9fd", "#ffb86c", "#ff79c6", "#bd93f9"],
			currentWordIndex: 0,
			currentColourIndex: 0,
		};
	},
	computed: {
		displayedWord() {
			return this.words[this.currentWordIndex];
		},
		currentColour() {
			return this.colours[this.currentColourIndex];
		},
	},
	mounted() {
		this.startRotation();
	},
	methods: {
		startRotation() {
			setInterval(() => {
				this.currentWordIndex = (this.currentWordIndex + 1) % this.words.length;
				this.currentColourIndex =
					(this.currentColourIndex + 1) % this.colours.length;
			}, 2000);
		},
	},
};
</script>
