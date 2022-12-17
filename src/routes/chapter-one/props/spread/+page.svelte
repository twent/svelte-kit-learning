<script>
	import { HomeLink, RepoInfo } from '$lib/index'

	const repoData = {
		name: 'svelte-kit-learning',
		author: 'twent',
		version: 0.1,
		language: 'js'
	}
</script>

<RepoInfo {...repoData} />

<!-- This is require more code
<RepoInfo name={pkg.name} version={pkg.version} speed={pkg.speed} website={pkg.link} />-->

<HomeLink />
