<script>
	import { onMount } from 'svelte';
	import { fade, fly } from 'svelte/transition';
	import { Rive } from '@rive-app/canvas';
	import { pathPercentage, colWidth } from '$lib/stores';
	import RiveActual from './RiveActual.svelte';

	export let column, startTime, title, colour;
</script>

<div
	style="grid-column-start: {column}"
	class="col-span-1 aspect-square row-start-4 w-full justify-center items-center sm:mt-8 md:mt-16 lg:mt-24 xl:mt-32"
>
	{#if $pathPercentage > startTime}
		<RiveActual />
	{/if}
</div>

<div
	style="grid-column-start: {column}; color: #{colour}"
	class="row-start-5 mt-8 col-span-2 mb-32"
>
	{#if $pathPercentage > startTime}
		<h1
			transition:fly={{ duration: 2000 }}
			class="gilroy sm:text-xl md:text-2xl lg:text-3xl xl:text-4xl 2xl:text-6xl tracking-tight"
		>
			{title}
		</h1>
		<div transition:fly={{ duration: 2200 }} class="!text-xs xl:!text-base">
			<slot />
		</div>
	{/if}
</div>
