<script>
	// components
	import Colors from './Colors';
	import Eyelet from './Eyelet';
	import Quantity from './Quantity';
	import Select from 'svelte-select';
	import Wired from './Wired';

	// props
	export let item;
	const items = [
		{ value: 'paper', label: 'Paper' },
		{ value: 'tyvek', label: 'Tyvek' }
	];
	let selectedValue;

	const handleClear = () => (selectedValue = undefined);
	const handleSelect = (e) => {
		selectedValue = e.detail;
		item.stock = selectedValue.value;
	};
</script>

<Quantity bind:item />
<div class="flex flex-col flex-grow">
	<div>Stock</div>
	<Select {items} {selectedValue} on:clear={handleClear} on:select={handleSelect} />
</div>
<Colors bind:item />
<Eyelet bind:item />
<Wired bind:item />
