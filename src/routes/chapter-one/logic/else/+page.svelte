<script>
	import { HomeLink } from '$lib/index'

	let user = { loggedIn: false }

	function toggle() {
		user.loggedIn = !user.loggedIn
	}
</script>

{#if user.loggedIn}
	<button on:click={toggle}> Log out </button>
{:else}
	<button on:click={toggle}> Log in </button>
{/if}

<HomeLink />
