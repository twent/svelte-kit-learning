<script>
	import { Thing } from '$lib/index'

	let things = [
		{ id: 1, name: 'apple' },
		{ id: 2, name: 'banana' },
		{ id: 3, name: 'carrot' },
		{ id: 4, name: 'doughnut' },
		{ id: 5, name: 'egg' }
	]

	function handleClick() {
		things = things.slice(1)
	}
</script>

<a href="#" role="button" on:click={handleClick}>Remove first thing</a>

{#each things as thing (thing.id)}
	<Thing name={thing.name} />
{/each}
