<script>
	import { colWidth } from '$lib/stores';
	let y;
</script>

<svelte:window bind:scrollY={y} />

<div
	class="h-[calc(100%-4rem)] grid fixed -z-50 overflow-hidden w-[calc(100%-4rem)] max-w-full grid-cols-12 gap-1"
>
	<div bind:offsetWidth={$colWidth} class="gridcol" />
	<div class="gridcol" />
	<div class="gridcol" />
	<div class="gridcol" />
	<div class="gridcol" />

	<div class="gridcol" />
	<div class="gridcol" />
	<div class="gridcol" />
	<div class="gridcol" />
	<div class="gridcol" />
	<div class="gridcol" />
	<!-- <div class="gridcol">
		<div style="transform: translate(0,{y*y*0.01}px)"
		class="border-t bg-[url('/grid1-white.png')] mt-24 col-start-6 col-span-1 h-[35vw] -mb-[30vw] -z-50"></div>
	</div>
	<div class="gridcol">
		<div style="transform: translate(0,{y*y*0.009}px)"
		class="border-t bg-[url('/grid1-white.png')] mt-24 col-start-6 col-span-1 h-[35vw] -mb-[30vw] -z-50"></div>
	</div>
	<div class="gridcol">
		<div style="transform: translate(0,{y*y*0.008}px)"
		class="border-t bg-[url('/grid1-white.png')] mt-24 col-start-6 col-span-1 h-[35vw] -mb-[30vw] -z-50"></div>
	</div>
	<div class="gridcol">
		<div style="transform: translate(0,{y*y*0.007}px)"
		class="border-t bg-[url('/grid1-white.png')] mt-24 col-start-6 col-span-1 h-[35vw] -mb-[30vw] -z-50"></div>
	</div>
	<div class="gridcol">
		<div style="transform: translate(0,{y*y*0.006}px)"
		class="border-t bg-[url('/grid1-white.png')] mt-24 col-start-6 col-span-1 h-[35vw] -mb-[30vw] -z-50"></div>
	</div>
	<div class="gridcol">
		<div style="transform: translate(0,{y*y*0.005}px)"
		class="border-t bg-[url('/grid1-white.png')] mt-24 col-start-6 col-span-1 h-[35vw] -mb-[30vw] -z-50"></div>
	</div> -->
	<div class="gridcol" />
</div>

<style type="text/postcss">
	.gridcol {
		@apply opacity-20 bg-slate-500 bg-opacity-30;
	}
</style>
