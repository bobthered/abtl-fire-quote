<script>
	// props
	export let href = '';
	export let color = 'blue';
	let colorClasses = '';

	$: if (color === 'blue') {
		colorClasses = 'bg-blue-500 hover:bg-blue-600 focus:ring-blue-500';
	} else if (color === 'red') {
		colorClasses = 'bg-red-500 hover:bg-red-600 focus:ring-red-500';
	}
</script>

<a
	{href}
	on:click
	class="p-2 rounded-full text-white transition duration-200 outline-none focus:ring focus:ring-opacity-30 {colorClasses}"
>
	<slot />
</a>
