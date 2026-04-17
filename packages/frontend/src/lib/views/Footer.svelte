<script lang="ts">
	import ThemeToggle from '$lib/ui/ThemeToggle.svelte'
        import { status } from '$lib/stores/status'
</script>

<footer>
	<ThemeToggle />
	<nav>
		<a href="/">/home</a>
		<a href="/about">/about</a>
		{#if $status?.imprint_url}
			<a href={$status.imprint_url} target="_blank" rel="noopener noreferrer">/imprint</a>
		{:else if $status?.imprint_html}
			<a href="/imprint">/imprint</a>
		{/if}
		<a href="https://github.com/cupcakearmy/cryptgeon" target="_blank" rel="noopener noreferrer">
			code
		</a>
		<span class="brand" aria-hidden="true">
			<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 120 144" fill="none">
				<path d="M48 12 L72 12 L82 28 L60 56 L38 28 Z" fill="#59BF8F" />
				<g stroke="currentColor" stroke-width="24" stroke-linecap="round">
					<line x1="32" y1="80" x2="88" y2="132" />
					<line x1="88" y1="80" x2="32" y2="132" />
				</g>
			</svg>
		</span>
	</nav>
</footer>

<style>
	footer {
		display: flex;
		justify-content: space-between;
		padding: 1rem;
		position: fixed;
		bottom: 0;
		right: 0;
		width: 100%;
		background-color: var(--ui-bg-0-85);
		backdrop-filter: blur(2px);
	}

	a {
		margin: 0 0.5rem;
	}

	nav {
		display: flex;
		flex-direction: row;
		justify-content: flex-end;
		align-items: center;
	}

	.brand {
		display: inline-flex;
		align-items: center;
		margin-left: 0.5rem;
		color: var(--ui-text-0);
	}

	.brand svg {
		height: 1.4rem;
		width: auto;
	}
</style>
