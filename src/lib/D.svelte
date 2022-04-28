<script lang="ts">
	import { onMount } from "svelte";
	import { ds, dsOpacity, colWidth } from '$lib/stores';

	export let aligner = false;
	export let colStart;
	export let delay;
	let init = false;
	let dsElement, dsContainer: HTMLElement;
	let offsetHeight;
	onMount(() => {
		$ds = dsElement.offsetTop - 32 + (offsetHeight / 2);
		init = true;
	})

	$: if (init && aligner) $ds = dsElement.offsetTop - 32 + (offsetHeight / 2);
	// $: if (init) dsContainer.style.opacity = $dsOpacity[0]
</script>

<div bind:this={dsContainer} style="grid-column-start: {colStart}; animation-delay: {delay}ms"
	class="col-span-1 aspect-square row-start-4 bg-slate-200 rounded-full border-slate-100 border flex w-full justify-center items-center mt-32">
	<div bind:this={dsElement} bind:offsetHeight class="w-2/5 max-h-full">
		<slot/>
	</div>
</div>