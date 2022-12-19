<script>
	let m = { x: 0, y: 0 }
</script>

<div on:mousemove={(e) => (m = { x: e.clientX, y: e.clientY })}>
	<h3>The mouse position is {m.x} x {m.y}</h3>
</div>

<style>
	div {
		padding: 10rem 0rem;
	}
</style>
