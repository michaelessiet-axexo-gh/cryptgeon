<script lang="ts">
	import { status } from '$lib/stores/status'
	import AboutParagraph from '$lib/ui/AboutParagraph.svelte'
</script>

<svelte:head>
	<title>About — Axexo</title>
</svelte:head>

<section class="content">
	<div class="mark" aria-hidden="true">
		<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 120 144" fill="none">
			<path d="M48 12 L72 12 L82 28 L60 56 L38 28 Z" fill="#59BF8F" />
			<g stroke="currentColor" stroke-width="24" stroke-linecap="round">
				<line x1="32" y1="80" x2="88" y2="132" />
				<line x1="88" y1="80" x2="32" y2="132" />
			</g>
		</svg>
	</div>

	<h1>About</h1>

	<p>
		<i>Axexo</i> is a secure note and file sharing tool, built on the open-source
		<a href="https://github.com/cupcakearmy/cryptgeon" target="_blank" rel="noopener noreferrer"
			>cryptgeon</a
		> project.
	</p>

	<AboutParagraph title="how does it work?">
		<span>
			each note has a generated <code>id (256bit)</code> and <code>key 256(bit)</code>. The
			<code>id</code>
			is used to save & retrieve the note. the note is then encrypted with aes in gcm mode on the client
			side with the <code>key</code> and then sent to the server. data is stored in memory and never
			persisted to disk. the server never sees the encryption key and cannot decrypt the contents of
			the notes even if it tried to.
		</span>
	</AboutParagraph>

	<AboutParagraph title="features">
		<ul>
			<li>server cannot decrypt contents due to client side encryption</li>
			<li>view and time constraints</li>
			<li>in memory, no persistence</li>
		</ul>
	</AboutParagraph>

	<AboutParagraph title="tech stack">
		<span>
			the backend is written in rust and the frontend is svelte and typescript.
			<br />
			you are welcomed to check & audit the
			<a href="https://github.com/cupcakearmy/cryptgeon" target="_blank" rel="noopener noreferrer">
				source code</a
			>.
		</span>
	</AboutParagraph>

	<AboutParagraph title="translations">
		<span
			>translations are managed on <a
				href="https://lokalise.com/"
				target="_blank"
				rel="noopener noreferrer">Lokalise</a
			>, which granted an open source license to the upstream project.
		</span>
	</AboutParagraph>

	<AboutParagraph title="attribution">
		<span>
			icons made by <a href="https://www.freepik.com" title="Freepik">freepik</a> from
			<a href="https://www.flaticon.com/" title="Flaticon">www.flaticon.com</a>
		</span>
	</AboutParagraph>

	<AboutParagraph title="version">
		<span>
			{#if $status}
				<code>v{$status.version}</code>
			{/if}
		</span>
	</AboutParagraph>
</section>

<style>
	section {
		width: 100%;
		display: flex;
		flex-direction: column;
		gap: 2rem;
	}

	.mark {
		display: flex;
		justify-content: center;
		margin-bottom: -1rem;
	}

	.mark svg {
		width: 4rem;
		height: auto;
		color: var(--ui-text-0);
	}

	ul {
		margin: 0;
		padding: 0;
		padding-left: 1rem;
		list-style: square;
	}
</style>
