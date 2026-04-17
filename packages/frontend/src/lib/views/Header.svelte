<script lang="ts">
	import { status } from '$lib/stores/status'

	function reset() {
		window.location.reload()
	}
</script>

<header>
	<a onclick={reset} href="/" aria-label="Axexo home">
		{#if $status?.theme_image}
			<img alt="logo" src={$status.theme_image} />
		{:else}
			<svg
				xmlns="http://www.w3.org/2000/svg"
				viewBox="0 0 450 200"
				role="img"
				aria-label="Axexo"
				fill="none"
			>
				<!-- Icon mark: green pentagon/gem crown + bold X -->
				<g transform="translate(22, 20)">
					<path d="M56 0 L104 0 L122 28 L80 72 L38 28 Z" fill="#59BF8F" />
					<g stroke="currentColor" stroke-width="30" stroke-linecap="round">
						<line x1="34" y1="98" x2="126" y2="158" />
						<line x1="126" y1="98" x2="34" y2="158" />
					</g>
				</g>
				<!-- Wordmark -->
				<text
					x="186"
					y="130"
					font-family="'Fira Mono', ui-monospace, 'SFMono-Regular', Menlo, monospace"
					font-size="82"
					font-weight="500"
					fill="currentColor"
					letter-spacing="2">AXEXO</text
				>
			</svg>
		{/if}
	</a>
</header>

<style>
	a {
		border: none;
		display: inline-block;
	}

	header {
		text-align: center;
		margin-top: 3rem;
		margin-bottom: 2rem;
	}

	img {
		object-fit: contain;
	}

	@media screen and (max-width: 30rem) {
		header {
			margin-top: 1rem;
			margin-bottom: 1rem;
		}

		header svg,
		header img {
			max-height: 4rem;
		}
	}

	header svg,
	header img {
		width: 100%;
		max-height: 7rem;
		fill: currentColor;
	}
</style>
