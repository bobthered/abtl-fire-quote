<script>
	// components
	import Select from 'svelte-select';

	// props
	export let item;
	let colors = [
		'Blue (Dark)',
		'Blue (Light)',
		'Brown',
		'Buff',
		'Gray',
		'Green (Dark)',
		'Green (Light)',
		'Ivory',
		'Lilac',
		'Manila',
		'Orange',
		'Pink',
		'Red',
		'Salmon',
		'White',
		'Yellow',
		'Fluorescent Yellow',
		'Fluorescent Green',
		'Fluorescent Orange',
		'Fluorescent Pink',
		'Fluorescent Red'
	];
	$: items = colors.map((color) => {
		return { value: color, label: color };
	});
	let selectedValue;

	const handleClear = () => (selectedValue = undefined);
	const handleSelect = (e) => {
		selectedValue = e.detail;
		item.color = selectedValue.value;
	};
</script>

<div class="flex flex-col flex-grow">
	<div>Color</div>
	<Select {items} {selectedValue} on:clear={handleClear} on:select={handleSelect} />
</div>
