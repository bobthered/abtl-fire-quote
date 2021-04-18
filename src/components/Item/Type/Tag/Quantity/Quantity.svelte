<script>
	// components
	import Select from 'svelte-select';

	// props
	export let item;
	let items = new Array(250).fill(0).map((_, i) => {
		return { value: i + 1, label: `${i + 1}M` };
	});
	let selectedValue;

	const handleClear = () => (selectedValue = undefined);
	const handleSelect = (e) => {
		selectedValue = e.detail;
		item.quantity = selectedValue.value;
	};
</script>

<div class="flex flex-col flex-grow">
	<div>Quantity</div>
	<Select {items} {selectedValue} on:clear={handleClear} on:select={handleSelect} />
</div>
