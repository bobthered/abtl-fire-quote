<script>
	// components
	import * as Button from '$components/Button';
	import Icon, { Duplicate, Trash } from 'svelte-hero-icons';
	import Type from './Type';

	// libraries
	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();

	// props
	export let i;
	export let item;

	const handleDelete = () => {
		dispatch('delete', { i });
	};
</script>

<div class="flex space-x-4 items-end shadow p-4">
	<Button.Group>
		<a
			href="#"
			on:click|preventDefault={handleDelete}
			class="rounded-l bg-red-500 text-white p-2 outline-none transition duration-200 hover:bg-red-600 focus:ring focus:ring-red-500 focus:ring-opacity-30"
		>
			<Icon src={Trash} class="w-6 h-6" />
		</a>
		<a
			href="#"
			on:click|preventDefault
			class="rounded-r bg-blue-500 text-white p-2 outline-none transition duration-200 hover:bg-blue-600 focus:ring focus:ring-blue-500 focus:ring-opacity-30"
		>
			<Icon src={Duplicate} class="w-6 h-6" />
		</a>
	</Button.Group>
	<Type bind:item />
</div>
