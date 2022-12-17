<script>
	export let name
	export let author
	export let version
	export let language

	$: href = `https://github.com/${author}/${name}`
</script>

<p>
	The <code>{name}</code> repo uses {language.toUpperCase()} language.
	<br />Download version {version} from <a {href} target="blank">Github</a>
</p>

<style>
	code {
		font-family: Menlo;
		padding: 0.1em 0.2em;
		border-radius: 0.2em;
	}
</style>
