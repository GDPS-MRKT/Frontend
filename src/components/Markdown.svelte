<script>
	import SvelteMarkdown, { allowHtmlOnly } from '@humanspeak/svelte-markdown';
	import hr from './Markdown/hr.svelte';
	import a from './Markdown/a.svelte';
	import img from './Markdown/img.svelte';
	import RawData from './Markdown/RawData.svelte';
	
	let { source } = $props();
	
	const noHTML = allowHtmlOnly([]);
</script>

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