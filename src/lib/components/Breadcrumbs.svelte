<script>
	import { page } from '$app/stores'
	import { afterUpdate } from 'svelte'

	/**
	 * @type {any[]}
	 */
	let breadcrumbs = []

	afterUpdate(async () => {
		let pathname = $page.url.pathname
		let paths = pathname.split('/')

		// remove the last element if there was a / at the end of the pathname
		paths = paths[paths.length - 1] === '' ? paths.slice(0, paths.length - 1) : paths

		// remove the first element if the second one is an empty string which means that we are in the root of the website
		paths = paths[0] === '' ? paths.slice(1) : paths

		breadcrumbs = paths.map((path, index) => {
			// Build the path for the current URL
			let url = '/' + paths.slice(0, index + 1).join('/')
			// Build caption with replacing slashes
			let caption = path.replace(/-/g, ' ')

			// HTML structure for every link except the first
			return `<li><a style="text-transform: capitalize;" href=${url}>${caption}</a></li>`
		})
	})
</script>

<nav aria-label="breadcrumb">
	<ul>
		<li><a href="/">Home</a></li>
		{#each breadcrumbs as breadcrumb}
			{@html breadcrumb}
		{/each}
	</ul>
</nav>
