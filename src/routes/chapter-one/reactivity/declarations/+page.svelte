<script>
	import { HomeLink } from '$lib/index.js'

	let count = 0
	$: doubled = count * 2

	function increment() {
		return count++
	}
</script>

<button on:click={increment}>
	Clicked {count}
	{count === 1 ? 'time' : 'times'}
</button>

<p>{count} doubled is {doubled}</p>

<HomeLink />
