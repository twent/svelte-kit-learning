<script>
	import { Outer } from '$lib/index'

	function handleMessage(event) {
		alert(event.detail.text)
	}
</script>

<Outer on:message={handleMessage} />

<br />

<div>
	<blockquote>
		Unlike DOM events, component events don't <em>bubble</em>. If you want to listen to an event on
		some deeply nested component, the intermediate components must <em>forward</em> the event.
	</blockquote>

	<p>
		In this case, we have the same <code data-file="/src/lib/App.svelte">App.svelte</code> and
		<code data-file="/src/lib/Inner.svelte">Inner.svelte</code>
		as in the <a href="/chapter-one/events/components">previous chapter</a>, but there's now an
		<code data-file="/src/lib/Outer.svelte">Outer.svelte</code>
		component that contains <code>&lt;Inner/&gt;</code>.
	</p>

	<p>
		One way we could solve the problem is adding <code>createEventDispatcher</code> to
		<code data-file="/src/lib/Outer.svelte">Outer.svelte</code>, listening for the
		<code>message</code> event, and creating a handler for it:
	</p>

	<p>
		But that's a lot of code to write, so Svelte gives us an equivalent shorthand — an <code
			>on:message</code
		>
		event directive without a value means 'forward all <code>message</code> events'.
	</p>
</div>
