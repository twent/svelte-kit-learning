<script>
	let user = { loggedIn: false }

	function toggle() {
		user.loggedIn = !user.loggedIn
	}
</script>

{#if user.loggedIn}
	<a href="#" role="button" on:click={toggle}> Log out </a>
{:else}
	<a href="#" role="button" on:click={toggle}> Log in </a>
{/if}
