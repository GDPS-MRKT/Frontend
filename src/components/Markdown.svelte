<script>
	import SvelteMarkdown, { allowHtmlOnly } from '@humanspeak/svelte-markdown';
	import hr from './Markdown/hr.svelte';
	import a from './Markdown/a.svelte';
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
		image: RawData,
	}}
/>