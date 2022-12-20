<script>
	import { page } from '$app/stores'
	import { Breadcrumbs, HomeLink } from '$lib/index'
</script>

<main>
	<!-- Header Nav -->
	<nav>
		<ul>
			<li>
				<a href="/" role="button"><strong>SvelteKit Learning</strong></a>
			</li>
		</ul>
		<ul>
			<li>
				<a href="https://github.com/twent" target="_blank" class="secondary">Github</a>
			</li>
		</ul>
	</nav>

	<!-- Breadcrumbs -->
	{#if $page.url.pathname != '/'}
		<Breadcrumbs />
	{/if}

	<slot />

	{#if $page.url.pathname != '/'}
		<footer>
			<HomeLink />
		</footer>
	{/if}
</main>
