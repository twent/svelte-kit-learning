<script>
	let count = 0

	$: if (count >= 2) {
		console.log(`the count is ${count} - it's max`)
		alert('Count is dangerously high!')
		count = 0
	}

	function increment() {
		return count++
	}
</script>

<a href="#" role="button" on:click={increment}>
	Clicked {count}
	{count === 1 ? 'time' : 'times'}
</a>
