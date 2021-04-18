<script>
	// components
	import Select from 'svelte-select';
	import Tag from './Tag';

	// props
	export let item;
	let items = [
		{ value: 'collar', label: 'Collar' },
		{ value: 'fastener', label: 'Fastener' },
		{ value: 'label', label: 'Label' },
		{ value: 'tag', label: 'Tag' }
	];
	let selectedValue;

	const handleClear = () => (selectedValue = undefined);
	const handleSelect = (e) => {
		selectedValue = e.detail;
		item.type = selectedValue.value;
	};
</script>

<div class="flex flex-col flex-grow">
	<div>Type</div>
	<Select {items} {selectedValue} on:clear={handleClear} on:select={handleSelect} />
</div>
{#if selectedValue !== undefined && selectedValue.value === 'tag'}
	<Tag bind:item />
{/if}
