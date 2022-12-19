<script>
	import HomeLink from '$lib/components/HomeLink.svelte'

	let m = { x: 0, y: 0 }
</script>

<div on:mousemove={(e) => (m = { x: e.clientX, y: e.clientY })}>
	<h3>The mouse position is {m.x} x {m.y}</h3>
</div>

<HomeLink />

<style>
	div {
		padding: 10rem 0rem;
	}
</style>
