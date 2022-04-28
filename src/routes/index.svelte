<script>
	import Line from '$lib/Line.svelte';
	import Logo from '$lib/Logo.svelte';
	import LogoSpinner from '$lib/LogoSpinner.svelte';
	import { colWidth } from '$lib/stores';
	import DRive from '$lib/DRive.svelte';
	import Aligner from '$lib/Aligner.svelte';

	let x, y;
	let m = { x: 0, y: 0 };

	function mouseMove(event) {
		m.x = event.clientX;
		m.y = event.clientY;
	}
</script>

<svelte:window bind:scrollY={y} bind:innerWidth={x} />

<Line />

<div on:mousemove={mouseMove} class="grid w-full grid-cols-12 gap-x-1">
	<div class="col-span-1 col-start-2 mt-24">
		<Logo />
	</div>
	<div
		id="bggrid"
		style="transform: translate(0,{y / 5}px)"
		class="bg-[url('/grid1-white.png')] mt-24 col-start-6 col-span-6 h-[35vw] -mb-[30vw] -z-50 opacity-20"
	>
		<!-- <canvas class="" width="{$colWidth * 6 + 5 * 4}" height="{$colWidth * 4.6}"> -->
		<canvas class="" width={$colWidth * 6 + 5 * 4} height={$colWidth * 4.6} />
	</div>
	<div class="col-span-5 col-start-5 row-start-2 -z-40" style="transform: translate(0,-{y / 9}px)">
		<img
			alt="ProDisplay"
			width="364"
			height="272"
			src="/landing/prodisplay-display.svg"
			class="w-full"
		/>
		<div class="grid grid-cols-5 gap-1">
			<img src="/landing/prodisplay-stand.webp" alt="" srcset="" class="col-start-3" />
		</div>
	</div>
	<div
		class="col-span-5 col-start-5 row-start-2 -z-40 flex justify-center items-center aspect-[364/210]"
		style="transform: translate(0,-{y / 9}px)"
	>
		<LogoSpinner style="w-1/6" />
	</div>

	<div
		class="col-span-3 col-start-3 row-start-2 self-end -z-10"
		style="transform: translate(0,-{y / 7}px)"
	>
		<!-- <MacBookDisplay/> -->
		<img
			alt="Macbook Display"
			width="213"
			height="147"
			src="/landing/macbook-display.svg"
			class="w-full"
		/>
	</div>
	<div
		class="col-span-3 col-start-3 row-start-2 self-end -z-20"
		style="transform: translate(0,-{y / 7}px)"
	>
		<video
			id="flamebg"
			autoplay
			playsinline
			muted
			loop
			class="-z-40 aspect-[213/147] p-1 w-full h-full object-cover object-center overflow-hidden"
		>
			<source src="/landing/newgradient.mp4" type="video/mp4" />
		</video>
	</div>
	<div
		class="col-span-3 col-start-3 row-start-2 self-end -z-10 aspect-[213/147] flex justify-center items-center"
		style="transform: translate(0,-{y / 7}px)"
	>
		<LogoSpinner style="w-1/6" />
	</div>
	<div
		class="col-span-3 col-start-3 row-start-3 self-end"
		style="transform: translate(0,-{y / 6.6}px)"
	>
		<img
			alt="Macbook Base"
			width="500"
			height="20"
			src="/landing/macbook-base.png"
			class="w-full scale-110"
		/>
	</div>
	<div
		class="col-span-2 col-start-9 row-start-2 self-end"
		style="padding-right: 25%; transform: translate(0,-{y / 5}px)"
	>
		<img alt="iPad" src="/landing/ipad.svg" width="108" height="140" class="w-full -mb-2" />
	</div>
	<div
		class="col-span-2 col-start-9 row-start-2 self-end aspect-[271/351] flex mr-[25%] justify-center items-center"
		style="transform: translate(0,-{y / 5}px)"
	>
		<LogoSpinner style="w-1/3" />
	</div>
	<div
		class="col-span-1 col-start-10 row-start-2 self-end"
		style="padding-left: 33%; transform: translate(0,-{y / 4}px)"
	>
		<img alt="iPhone" src="/landing/iphone.svg" width="48" height="100" class="w-full -mb-4" />
	</div>
	<div
		class="col-span-1 col-start-10 row-start-2 self-end aspect-[12/25] flex justify-center items-center ml-[33%]"
		style="transform: translate(0,-{y / 4}px)"
	>
		<LogoSpinner style="w-[1/2] -mb-4" />
	</div>
	<Aligner />
	<DRive column="3" title="Dream" colour="EB9B27" startTime="67">
		<ul>
			<li>Idea Sharing</li>
			<li>Brainstorming</li>
			<li>Vulkan Mind Meld</li>
		</ul>
	</DRive>
	<DRive column="5" title="Design" colour="D66973" startTime="83">
		<ul>
			<li>UI / UX</li>
			<li>Responsive Web Design</li>
			<li>Logos &amp; Branding</li>
		</ul>
	</DRive>
	<DRive column="7" title="Develop" colour="A435E4" startTime="99">
		<ul>
			<li>HTML, CSS, JavaScript</li>
			<li>Frontend &amp; Backend</li>
			<li>Interaction Design</li>
		</ul>
	</DRive>
	<DRive column="9" title="Deploy" colour="7C69EE" startTime="115">
		<ul>
			<li>Serverless Computing</li>
			<li>Managed Content</li>
			<li>Ongoing Support</li>
		</ul>
	</DRive>
</div>

<style type="text/postcss">
	li {
		@apply mt-4 text-slate-400;
	}
</style>
