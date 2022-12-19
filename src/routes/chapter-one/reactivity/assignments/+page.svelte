<script>
	let count = 0

	function increment() {
		return count++
	}
</script>

<a href="#" role="button" on:click={increment}>
	Clicked {count}
	{count === 1 ? 'time' : 'times'}
</a>
