<script lang="ts">
	import 'virtual:uno.css';
	import '../app.css';
	import '../markdown.css';
	import '../animations.css';
	import StarsCanvas from '$lib/components/common/stars-canvas/stars-canvas.svelte';

	let { children } = $props();
</script>

<StarsCanvas />
<div class="flex min-h-screen flex-1 flex-col">{@render children()}</div>
