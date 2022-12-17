<script>
	import { HomeLink } from '$lib/index.js'

	let numbers = [1, 2, 3, 4]

	function addNumber() {
		// numbers.push(numbers.length + 1) - it's not works (reactive assignment not recieve data)
		numbers = [...numbers, numbers.length + 1] // - it's works
		// numbers[numbers.length] = numbers.length + 1 // - also works
	}

	$: sum = numbers.reduce((t, n) => t + n, 0)
</script>

<p>{numbers.join(' + ')} = {sum}</p>

<button on:click={addNumber}>Add a number</button>

<HomeLink />
