<script>
	let count = 0
	$: doubled = count * 2

	function increment() {
		return count++
	}
</script>

<a href="#" role="button" on:click={increment}>
	Clicked {count}
	{count === 1 ? 'time' : 'times'}
</a>

<p>{count} doubled is {doubled}</p>
