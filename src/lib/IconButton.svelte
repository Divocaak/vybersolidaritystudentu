<script>
	let { href, aria, text, children } = $props();
</script>

<a {href} aria-label={aria} target="_blank">
	<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" fill="currentColor">
		{@render children?.()}
	</svg>
	<span>
		{text}
	</span>
</a>

<style>
	a {
		display: inline-flex;
		align-items: center;
		justify-content: center;
		gap: 0.5em;
	}

	a svg {
		display: block;
		width: 1em;
		height: 1em;
		flex-shrink: 0;
	}
</style>
