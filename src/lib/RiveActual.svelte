<script>
	import { onMount } from 'svelte';
	import { Rive } from '@rive-app/canvas';
	import { colWidth } from '$lib/stores';

	let rive, canvas;

	onMount(async () => {
		rive = new Rive({
			src: '/landing/dream.riv',
			canvas: canvas,
			autoplay: true
		});
	});
</script>

<canvas
	width={($colWidth / 4) * 3}
	height={($colWidth / 4) * 3}
	bind:this={canvas}
	class="w-3/4 aspect-square"
/>
