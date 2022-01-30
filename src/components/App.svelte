<style>
	ul {
		list-style-type: none;
		padding: 0;
		margin: 0;
	}

	li {
		padding: 10px;
		border-bottom: 1px solid #ddd;
		animation: fadeIn 0.7s ease-in-out;
	}

	@keyframes fadeIn {
		0% {
			opacity: 0;
		}

		100% {
			opacity: 1;
		}
	}
</style>

<script>
	let name = 'svelte';

	let todos = [
		{ done: false, text: 'finish Svelte tutorial' },
		{ done: false, text: 'build an app' },
		{ done: false, text: 'world domination' }
	];

	const newTodo = () => {
		todos = [...todos, { done: false, text: 'Figure out svelte' }];
		return false;
	}
</script>

<input type="text" bind:value={name} />

<h1>Hello {name}!</h1>

<ul>
	{#each todos as todo}
		<li>
			<span>{todo.text}</span>
		</li>
	{/each}
</ul>

<button on:click={newTodo}>Add New</button>