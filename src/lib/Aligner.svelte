<script lang="ts">
	import { onMount } from "svelte";
	import { ds } from '$lib/stores';

	let init: boolean = false;
	let dsElement: HTMLElement;
	let offsetHeight: number;

	onMount(() => {
		$ds = dsElement.offsetTop - 32 + (offsetHeight / 2);
		init = true;
	})

	$: if (init) $ds = dsElement.offsetTop - 32 + (offsetHeight / 2);
	// $: if (init) dsContainer.style.opacity = $dsOpacity[0]
</script>

<div bind:this={dsElement} bind:offsetHeight class="col-span-1 col-start-1 aspect-square row-start-4 w-3/4 sm:mt-8 md:mt-16 lg:mt-24 xl:mt-32">
</div>