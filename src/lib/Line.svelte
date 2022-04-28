<script>
	import { afterUpdate, onMount } from 'svelte';
	import { lineStartHeight, colWidth, ds, dsOpacity, pathPercentage } from '$lib/stores';

	let init = false;
	let y,
		z = 0;
	let path,
		pathlength = 0,
		pathpos = 0;

	function pathEase(pos) {
		return pos * pos * 0.01;
	}

	let mypath = '';

	onMount(() => {
		let frame;

		function loop() {
			frame = requestAnimationFrame(loop);

			if (pathpos <= pathlength) pathpos += 5;

			$pathPercentage = (pathpos / pathlength) * 120; // 120% really :)
		}

		setTimeout(() => {
			path.style.opacity = 0.5;
			pathlength = path.getTotalLength();
			loop();
		}, 500); //3384
	});

	afterUpdate(() => {
		pathlength = path.getTotalLength();
		init = true;
	});

	$: if (y) pathlength = path.getTotalLength();

	$: if (y * 4 > pathpos) pathpos = y * 4;
</script>

<svelte:window bind:scrollY={y} />

<div class="absolute -z-50">
	<svg
		width={$colWidth * 12}
		height={$ds + 10}
		viewBox="0 0 {$colWidth * 12} {$ds + 10}"
		version="1.1"
		xmlns="http://www.w3.org/2000/svg"
		xmlns:xlink="http://www.w3.org/1999/xlink"
	>
		<circle
			id="logo-dot"
			stroke="#ffffff"
			fill="#999999"
			cx={$colWidth * 2 + $colWidth / 6}
			cy={$lineStartHeight}
			r="3"
		/>
		<path
			id="line"
			stroke="#ffffff"
			opacity="0"
			fill="none"
			bind:this={path}
			stroke-dasharray={pathlength}
			stroke-dashoffset={Math.max(pathlength - pathpos, 0)}
			d="	M {$colWidth * 2 + $colWidth / 6 + 2} {$lineStartHeight}
			h {$colWidth / 4}
			q {$colWidth / 2} 0 {$colWidth / 2} {$colWidth / 2}
			q 0 {$colWidth / 2} {-$colWidth / 2} {$colWidth / 2}
			h {-($colWidth / 4 + $colWidth - 4 - $colWidth / 2 + $colWidth / 6)}
			q {-$colWidth / 2} 0 {-$colWidth / 2} {$colWidth / 2}
			V {$ds - $colWidth / 2}
			q 0 {$colWidth / 2} {$colWidth / 2} {$colWidth / 2}
			h {$colWidth * 7 + 4 * 7}"
		/>
	</svg>
</div>

<style>
	#logo-dot {
		animation: flicker-in 3s linear;
		animation-delay: 384ms;
	}
	@keyframes flicker-in {
		0% {
			opacity: 0;
		}
		50% {
			opacity: 1;
		}
		51% {
			opacity: 0;
		}
		69% {
			opacity: 0;
		}
		70% {
			opacity: 1;
		}
		73% {
			opacity: 1;
		}
		74% {
			opacity: 0;
		}
		84% {
			opacity: 0;
		}
		85% {
			opacity: 1;
		}
		86% {
			opacity: 0;
		}
		89% {
			opacity: 0;
		}
		90% {
			opacity: 1;
		}
		91% {
			opacity: 0;
		}

		100% {
			opacity: 1;
		}
	}
</style>
