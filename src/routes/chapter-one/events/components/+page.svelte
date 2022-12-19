<script>
	import { Inner } from '$lib/index'

	function handleMessage(event) {
		alert(event.detail.text)
	}
</script>

<h3>Components can also dispatch events.</h3>

<Inner on:message={handleMessage} />

<blockquote>
	<p>
		<code>createEventDispatcher</code> must be called when the component is first instantiated — you
		can't do it later inside e.g. a <code>setTimeout</code> callback. This links
		<code>dispatch</code> to the component instance.
	</p>
</blockquote>

<p>
	Notice that the <code>App</code> component is listening to the messages dispatched by
	<code>Inner</code>
	component thanks to the <code>on:message</code> directive. This directive is an attribute prefixed
	with <code>on:</code> followed by the event name that we are dispatching (in this case,
	<code>message</code>).
</p>

<p>
	Without this attribute, messages would still be dispatched, but the App would not react to it. You
	can try removing the <code>on:message</code> attribute and pressing the button again.
</p>

<blockquote>
	<p>
		You can also try changing the event name to something else. For instance, change <code
			>dispatch('message')</code
		>
		to <code>dispatch('myevent')</code> in
		<code data-file="/src/lib/Inner.svelte">Inner.svelte</code>
		and change the attribute name from <code>on:message</code> to <code>on:myevent</code> in the
		<code data-file="/src/lib/App.svelte">App.svelte</code> component.
	</p>
</blockquote>
