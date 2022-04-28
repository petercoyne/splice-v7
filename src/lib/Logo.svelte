<script>
	import { lineStartHeight } from '$lib/stores';
	import { onMount } from 'svelte';
	let logoText;
	let init = false;
	let windowWidth;

	onMount(async () => {
		$lineStartHeight = logoText.offsetTop;
		init = true;
	});

	$: if (windowWidth) $lineStartHeight = logoText.offsetTop - 32 + logoText.offsetHeight/2;
</script>

<svelte:window bind:innerWidth={windowWidth}/>

<div class="flex flex-col gap-1 items-center aspect-[7/5]">
	<div class="grid grid-rows-1 grid-cols-1 w-1/2 aspect-sqare h-auto">
		<div class="row-start-1 col-start-1">
			<img src="/logo/ring-inner.svg" width="36" height="36" alt="" srcset="" class="w-full aspect-sqare" />
		</div>
		<div class="row-start-1 col-start-1 logospin1">
			<img src="/logo/ring-mid.svg" width="36" height="36" alt="" srcset="" class="w-full aspect-sqare" />
		</div>
		<div class="row-start-1 col-start-1 logospin2">
			<img src="/logo/ring-outer.svg" width="36" height="36" alt="" srcset="" class="w-full aspect-sqare" />
		</div>
	</div>

	<div bind:this={logoText} class="flex-grow mt-2 relative flex justify-between w-full">
		<img src="/logo/s.svg" alt="s" srcset="" width="11" height="14" class="h-full flicker-in flicker-1" />
		<img src="/logo/p.svg" alt="p" srcset="" width="10" height="14" class="h-full flicker-in flicker-2" />
		<img src="/logo/l.svg" alt="l" srcset="" width="9" height="14" class="h-full flicker-in flicker-3" />
		<img src="/logo/i.svg" alt="i" srcset="" width="4" height="14" class="h-full flicker-in flicker-4" />
		<img src="/logo/c.svg" alt="c" srcset="" width="13" height="14" class="h-full flicker-in flicker-5" />
		<img src="/logo/e.svg" alt="e" srcset="" width="9" height="14" class="h-full flicker-in flicker-6" />
	</div>
	<h1 class="hidden">Splice</h1>
</div>

<style>


	.flicker-in {
		animation: flicker-in 2s linear;
	}

	.flicker-1 {
		animation-delay: 0ms;
	}
	.flicker-2 {
		animation-delay: 64ms;
	}
	.flicker-3 {
		animation-delay: 128ms;
	}
	.flicker-4 {
		animation-delay: 192ms;
	}
	.flicker-5 {
		animation-delay: 256ms;
	}
	.flicker-6 {
		animation-delay: 320ms;
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
		100% {
			opacity: 1;
		}
	}
</style>
