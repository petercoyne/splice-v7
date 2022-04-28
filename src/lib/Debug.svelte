<script>
	let innerWidth, innerHeight;
	import { lineStartHeight, ds, pathPercentage } from '$lib/stores';
</script>

<svelte:window bind:innerWidth bind:innerHeight />
<div
	class="fixed bottom-0 left-0 z-50 bg-black bg-opacity-10 backdrop-blur-md text-red-500 p-4 m-2 rounded-md"
>
	<div class="uppercase text-xs text-sky-300">DEBUG {$pathPercentage}</div>
	<div class="sm:hidden">phone</div>
	<div class="hidden sm:block md:hidden">sm</div>
	<div class="hidden md:block lg:hidden">md</div>
	<div class="hidden lg:block xl:hidden">lg</div>
	<div class="hidden xl:block">xl</div>
	<div class="text-xs text-white">{innerWidth} x {innerHeight}</div>
</div>
