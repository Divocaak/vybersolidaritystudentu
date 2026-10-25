<script>
	import favicon from '#lib/assets/favicon.jpg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<nav>
	<a href="/#protest">protest</a>
	<a href="/#co-se-deje">co se děje</a>
	<a href="/#aktualni-prohlaseni">aktuální prohlášení</a>
	<a href="/#kontakty">kontakty</a>
</nav>

{@render children()}

<footer>
	<p class="signature">
		Designed, coded & maintained by
		<a href="https://divokyvojtech.cz/" target="_blank">Vojtěch Divoký</a>
	</p>
</footer>

<style>
	:global(:root) {
		--ui-scale: 1;

		--text-12: calc(clamp(0.6rem, 0.5rem + 0.2vw, 0.75rem) * var(--ui-scale));
		--text-16: calc(clamp(0.9rem, 0.8rem + 0.5vw, 1rem) * var(--ui-scale));
		--text-20: calc(clamp(1rem, 0.9rem + 0.6vw, 1.25rem) * var(--ui-scale));
		--text-24: calc(clamp(1.1rem, 1rem + 0.8vw, 1.5rem) * var(--ui-scale));
		--text-32: calc(clamp(1.3rem, 1.1rem + 1.2vw, 2rem) * var(--ui-scale));
		--text-36: calc(clamp(1.5rem, 1.2rem + 1.5vw, 2.25rem) * var(--ui-scale));
		--text-48: calc(clamp(1.8rem, 1.4rem + 2vw, 3rem) * var(--ui-scale));
		--text-64: calc(clamp(2.2rem, 1.8rem + 2.8vw, 4rem) * var(--ui-scale));
		--text-96: calc(clamp(3rem, 2.5rem + 4vw, 6rem) * var(--ui-scale));

		--gap: 5rem;

		--border-width: 5px;

		--color-primary: #243b64;
		--color-background: #f5f0e6;
		--color-text: #202321;
		--color-accent: #e9c84a;
		--color-secondary: #d8d3c8;

		--color-surface: #fffcf7;
		--color-text-muted: #625f58;
		--color-border: #d8d3c8;
	}

	:global(html) {
		scroll-behavior: smooth;
	}

	:global(body) {
		background-color: var(--color-background);
		color: var(--color-text);
	}

	:global(h1) {
		font-size: var(--text-48);
	}

	:global(p),
	:global(a) {
		font-size: var(--text-20);
		line-height: calc(var(--text-20) * 1.25);
	}

	:global(.attention-text) {
		background-color: var(--color-accent);
		font-weight: bold;
		padding: 5px 10px;
		border-radius: 5px;
	}

	nav {
		display: flex;
		flex-direction: row;
		justify-content: center;
		gap: var(--gap);

		padding: 1rem 0;

		border-bottom: var(--border-width) solid var(--color-primary);
	}

	footer,
	footer p,
	footer a {
		all: revert;
	}

	footer {
		margin-top: 400px;
	}

	footer p {
		text-align: end;
		font-size: xx-small;
	}

	:global(a) {
		text-decoration: none;
		text-transform: uppercase;
		font-weight: bold;
		color: #243b64;

		display: inline-block;
		vertical-align: middle;
		position: relative;

		transform: perspective(1px) translateZ(0);
		transition:
			transform 0.3s ease,
			color 0.2s ease;
	}

	:global(a:hover),
	:global(a:focus),
	:global(a:active) {
		transform: scale(1.1);
	}

	nav a::after {
		content: '';
		position: absolute;
		left: 0;
		bottom: -4px;
		width: 100%;
		height: 2px;
		background: currentColor;
		transform: scaleX(0);
		transform-origin: left;
		transition: transform 0.2s ease;
	}

	nav a:hover,
	nav a:focus-visible {
		color: #172744;
	}

	nav a:hover::after,
	nav a:focus-visible::after,
	nav a[aria-current='page']::after {
		transform: scaleX(1);
	}

	nav a:focus-visible {
		outline: 2px solid #243b64;
		outline-offset: 6px;
	}

	@media (max-width: 1023px) {
		:global(:root) {
			--gap: 1rem;
		}
	}

	@media (max-width: 599px) {
		:global(:root) {
			--gap: 1rem;
		}

		nav {
			flex-direction: column;
			padding-left: var(--gap);
		}
	}
</style>
