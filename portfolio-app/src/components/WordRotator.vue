<template>
	<div class="rotating-word">
		<p>{{ displayedWord }}</p>
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
			],
			currentWordIndex: 0,
		};
	},
	computed: {
		displayedWord() {
			return this.words[this.currentWordIndex];
		},
	},
	mounted() {
		this.startRotation();
	},
	methods: {
		startRotation() {
			setInterval(() => {
				this.currentWordIndex = (this.currentWordIndex + 1) % this.words.length;
			}, 2000);
		},
	},
};
</script>
