<script>
	import SvelteMarkdown, { allowHtmlOnly } from '@humanspeak/svelte-markdown';
	import hr from './Markdown/hr.svelte';
	import a from './Markdown/a.svelte';
	import img from './Markdown/img.svelte';
	import RawData from './Markdown/RawData.svelte';
	
	let { source } = $props();
	
	const noHTML = allowHtmlOnly([]);
</script>

<div class="markdownResult">
	<SvelteMarkdown
		{ source }
		renderers={{
			hr: hr,
			link: a,
			html: noHTML,
			image: img,
		}}
	>
		{#snippet paragraph({ children })}
			<p class="descElement">{@render children?.()}</p>
		{/snippet}
	</SvelteMarkdown>
</div>

<style>
	.markdownResult {
		display: contents;
	}
	
	h1,
	h2,
	:global .markdownResult h1,
	:global .markdownResult h2,
	:global .markdownResult h3,
	:global .markdownResult h4,
	:global .markdownResult h5,
	:global .markdownResult h6,
	:global .markdownResult p {
		color: var(--m3c-on-primary-container);
		
		margin: 0px;
		
		gap: 5px;
	}
	
	h1,
	:global .markdownResult h1 {
		font-size: 1.6rem;
		font-weight: 900;
	}
	
	h2,
	:global .markdownResult h2 {
		font-size: 1.4rem;
		font-weight: 800;
	}
	
	:global .markdownResult h3 {
		font-size: 1.2rem;
		font-weight: 700;
	}
	
	:global .markdownResult h4 {
		font-size: 1.1rem;
		font-weight: 600;
	}
	
	:global .markdownResult h5 {
		font-size: 1.1rem;
		font-weight: 500;
	}
	
	:global .markdownResult h6 {
		font-size: 1.1rem;
		font-weight: 400;
	}
	
	:global .markdownResult p {
		font-size: 1rem;
		color: var(--m3c-on-secondary-container);
	}
	
	:global .markdownResult ul {
		margin: 0px;
		padding: 0;
		padding-left: 2.5rem;
		
		color: var(--m3c-on-secondary-container);
	}
	
	:global .markdownResult ul:has(a) {
		font-size: 1.1rem;
		font-weight: 500;
		padding: 0 1rem;
	}
	
	:global .markdownResult li {
		margin: .2rem 0px;
		
		position: relative;
	}
	
	:global .markdownResult li > ul {
		font-size: 1rem;
	}
	
	:global .markdownResult a {
		text-decoration: none;
	}
	
	:global .markdownResult code {
		display: inline-flex;
		
		color: var(--m3c-tertiary);
		
		background: var(--m3c-surface-container);
		border-radius: var(--m3-shape-small);
		
		width: max-content;
		padding: .1rem .2rem;
		margin: -.1rem -.1rem;
		font-size: 0.8rem;
		
		overflow-wrap: anywhere;
		
		font-family: "Google Sans Code Variable";
	}
	
	:global .markdownResult h1 code {
		font-size: 1.4rem;
	}
	
	:global .markdownResult h2 code {
		font-size: 1.2rem;
	}
	
	:global .markdownResult h3 code {
		font-size: 1.1rem;
	}
	
	:global .markdownResult blockquote {
		margin: .25rem;
		margin-left: 15px;
		
		position: relative;
	}
	
	:global .markdownResult blockquote::before {
		content: "";
		display: block;
		
		height: 100%;
		width: 5px;
		
		background: var(--m3c-primary);
		border-radius: 100px;
		
		position: absolute;
		left: -15px;
	}
	
	:global .markdownResult pre {
		display: contents;
	}
	
	:global .markdownResult ol {
		margin: 0px;
		color: var(--m3c-on-secondary-container);
		padding-left: 2.5rem;
	}
	
	:global .markdownResult table,
	:global .markdownResult tbody {
		display: flex;
		flex-direction: column;
		gap: 3px;
	}
	
	:global .markdownResult tr {
		display: flex;
		gap: 3px;
	}
	
	:global .markdownResult thead th {
		display: block;
		
		border-radius: var(--m3-shape-small);
		
		background: var(--m3c-primary-container);
		color: var(--m3c-on-primary-container);
		
		width: 100%;
		padding: .5rem;
	}
	
	:global .markdownResult tbody td {
		display: block;
		
		border-radius: var(--m3-shape-small);
		
		background: var(--m3c-secondary-container);
		color: var(--m3c-on-secondary-container);
		
		width: 100%;
		padding: .5rem;
	}
	
	:global .markdownResult thead th:nth-of-type(1) {
		border-top-left-radius: var(--m3-shape-large);
	}
	
	:global .markdownResult thead th:nth-last-of-type(1) {
		border-top-right-radius: var(--m3-shape-large);
	}
	
	:global .markdownResult tbody tr:nth-last-of-type(1) td:nth-of-type(1) {
		border-bottom-left-radius: var(--m3-shape-large);
	}
	
	:global .markdownResult tbody tr:nth-last-of-type(1) td:nth-last-of-type(1) {
		border-bottom-right-radius: var(--m3-shape-large);
	}
	
	:global .markdownResult object {
		border-radius: var(--m3-shape-large);
		
		max-height: 55vh;
		max-width: fit-content;
	}
	
	:global dialog .markdownResult object {
		max-height: 35vh;
	}
	
	:global .markdownResult .descElement {
		display: ruby;
	}
</style>