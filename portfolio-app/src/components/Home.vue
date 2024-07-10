<template>
	<div class="welcome">
		<p>Hi</p>
		<p>I'm Gareth Austin</p>
		<RotatingWords />
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
