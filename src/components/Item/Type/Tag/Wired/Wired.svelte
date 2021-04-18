<script>
	// components
	import Checkbox from 'svelte-checkbox';

	// props
	export let item;
	$: if (!('wired' in item)) item.wired = false;
</script>

<div class="flex flex-col">
	<div>Wired</div>
	<Checkbox bind:checked={item.wired} />
</div>
