<script>
	// components
	import Checkbox from 'svelte-checkbox';

	// props
	export let item;
	$: if (!('eyelet' in item)) item.eyelet = false;
</script>

<div class="flex flex-col">
	<div>Eyelet</div>
	<Checkbox bind:checked={item.eyelet} />
</div>
