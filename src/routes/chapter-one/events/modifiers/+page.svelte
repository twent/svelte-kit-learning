<script>
	function handleClick() {
		alert('no more alerts')
	}
</script>

<h3>DOM event handlers can have <em>modifiers</em> that alter their behaviour.</h3>
<p>For example, a handler with a <code>once</code> modifier will only run a single time:</p>

<a href="#" role="button" on:click|once|capture={handleClick}> Click me </a>

<h4>The full list of modifiers:</h4>
<ul>
	<li>
		<code>preventDefault</code> — calls <code>event.preventDefault()</code> before running the handler.
		Useful for client-side form handling, for example.
	</li>
	<li>
		<code>stopPropagation</code> — calls <code>event.stopPropagation()</code>, preventing the event
		reaching the next element
	</li>
	<li>
		<code>passive</code> — improves scrolling performance on touch/wheel events (Svelte will add it automatically
		where it's safe to do so)
	</li>
	<li><code>nonpassive</code> — explicitly set <code>passive: false</code></li>
	<li>
		<code>capture</code> — fires the handler during the <em>capture</em> phase instead of the
		<em>bubbling</em>
		phase (<a
			href="https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#Event_bubbling_and_capture"
			>MDN docs</a
		>)
	</li>
	<li><code>once</code> — remove the handler after the first time it runs</li>
	<li><code>self</code> — only trigger handler if event.target is the element itself</li>
	<li>
		<code>trusted</code> — only trigger handler if <code>event.isTrusted</code> is
		<code>true</code>. I.e. if the event is triggered by a user action.
	</li>
</ul>
<p>You can chain modifiers together, e.g. <code>on:click|once|capture={'{'}...{'}'}</code>.</p>
