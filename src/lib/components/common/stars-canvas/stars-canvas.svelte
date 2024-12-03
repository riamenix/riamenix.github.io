<script lang="ts">
	import mountNightStarsAnimation from '$lib/animations/night-stars';
	import { onMount } from 'svelte';

	onMount(() => {
		const canvas = document.getElementById('bg-stars') as HTMLCanvasElement;

		mountNightStarsAnimation(canvas);
	});
</script>

<div class="fixed top-0 z-[-1]">
	<canvas id="bg-stars" class="h-screen w-screen"></canvas>
</div>
