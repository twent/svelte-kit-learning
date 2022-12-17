<script>
	import { HomeLink } from '$lib/index'

	let x = 4
	function increment() {
		return x++
	}
</script>

{#if x > 10}
	<p>{x} is greater than 10</p>
{:else if 5 > x}
	<p>{x} is less than 5</p>
{:else}
	<p>{x} is between 5 and 10</p>
{/if}

<button on:click={increment}>
	{x} + 1
</button>

<HomeLink />
