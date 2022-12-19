<script>
	import { page } from '$app/stores'
	import navigationData from '$lib/data/navigation.json'

	let pathname = $page.url.pathname
	var paths = pathname.split('/')

	// remove the last element if there was a / at the end of the pathname
	paths = paths[paths.length - 1] === '' ? paths.slice(0, paths.length - 1) : paths

	// remove the first element if the second one is an empty string which means that we are in the root of the website
	paths = paths[0] === '' ? paths.slice(1) : paths

	let breadcrumbs = paths.map((path, index) => {
		// Build the path for the current URL
		var url = '/' + paths.slice(0, index + 1).join('/')

		// HTML structure for every link except the first
		return `<li><a key=${index} href=${url}>${path}</a></li>`
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
