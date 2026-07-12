<script>
	import { Dialog, Button } from "m3-svelte";
    const { href = '', title = undefined, children } = $props();
	
	let open = $state(false);
	
	function openDialog(event) {
		if(href.startsWith("#")) return;
		
		event.preventDefault();
		event.stopPropagation();
		
		if(!href.startsWith("http:") && !href.startsWith("https:")) return;
		
		open = true;
	}
	
	function openLink(href) {
		const newPage = document.createElement("a");
		newPage.href = href;
		newPage.target = "_blank";
		newPage.rel = "noopener noreferrer";
		console.log(newPage);
		newPage.click();
	}
</script>

<a
	{href}
    on:click={openDialog}
    {title}
>
    {@render children?.()}
</a>
<Dialog headline="External link" bind:open>
	Are you sure you want to open this link?<br>
	<code>
		{href}
	</code>
	{#snippet buttons()}
		<Button variant="filled">Go back</Button>
		<Button variant="tonal" onclick={() => openLink(href)}>Open</Button>
	{/snippet}
</Dialog>

<style>
	a {
		cursor: pointer;
		color: -webkit-link;
	}
</style>