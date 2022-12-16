<script>
	import { HomeLink } from '$lib/index.js'

	let count = 0

	function increment() {
		return count++
	}
</script>

<button on:click={increment}>
	Clicked {count}
	{count === 1 ? 'time' : 'times'}
</button>

<HomeLink />
