<script>
import BackgroundGrid from '$lib/BackgroundGrid.svelte';
import Debug from '$lib/Debug.svelte';

	import '../app.css';
</script>

<Debug/>
<BackgroundGrid/>
<div class="hidden sm:block">
	<slot />
</div>

<div class="block sm:hidden">
	No mobile version yet :/
</div>