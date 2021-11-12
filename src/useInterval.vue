<template>
	<div>
		<p>Interval fired: {{ counter }}</p>
	</div>
</template>
<script setup lang="ts">
import { useInterval } from "@vueuse/core";
const { counter, pause, resume } = useInterval(200, { controls: true });

let i = 0;
window.addEventListener("click", () => {
	if (++i % 2) {
		pause();
	} else {
		resume();
	}
});
</script>
