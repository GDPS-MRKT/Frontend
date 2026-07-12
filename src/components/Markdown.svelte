<script>
	import SvelteMarkdown from '@humanspeak/svelte-markdown';
	import hr from './Markdown/hr.svelte';
	import a from './Markdown/a.svelte';
	import RawData from './Markdown/RawData.svelte';
	
	let { source } = $props();
</script>

<SvelteMarkdown
	{ source }
	renderers={{
		hr: hr,
		link: a,
		image: RawData 
	}}
/>