<script>
	// components
	import * as Button from '$components/Button';
	import Icon, { Plus } from 'svelte-hero-icons';
	import Item from '$components/Item';

	// props
	let items = [];

	const add = (e) => {
		e.preventDefault();
		items = [...items, {}];
	};
	const handleDelete = (e) => {
		const filteredItems = [...items].filter((_, i) => i != e.detail.i);
		items = filteredItems;
		console.log(items);
	};
</script>

<div class="w-screen h-screen bg-white p-4">
	<div class="flex flex-col space-y-8">
		<div class="flex justify-end">
			<Button.Icon href="/add" on:click={add}>
				<Icon src={Plus} class="w-6 h-6" />
			</Button.Icon>
		</div>
		{#each items as i}
			<Item bind:item {i} on:delete={handleDelete} />
		{/each}
	</div>
</div>
