<script>
	let m = { x: 0, y: 0 }

	function handleMousemove(event) {
		m.x = event.clientX
		m.y = event.clientY
	}
</script>

<div on:mousemove={handleMousemove}>
	<h3>The mouse position is {m.x} x {m.y}</h3>
</div>

<style>
	div {
		padding: 10rem 0rem;
	}
</style>
