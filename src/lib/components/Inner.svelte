<script>
	import { createEventDispatcher } from 'svelte'

	const dispatch = createEventDispatcher()

	function sayHello() {
		dispatch('message', {
			text: 'Hello!'
		})
	}
</script>

<a href="#" role="button" on:click={sayHello}> Click to say hello </a>
