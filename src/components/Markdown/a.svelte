<script>
	import { Dialog, Button } from "m3-svelte";
    const { href = '', title = undefined, children } = $props();
	
	let open = $state(false);
	
	function isCorrectLink(href) {
		if(!href.startsWith("http:") && !href.startsWith("https:")) return false;
		
		return true;
	}
	
	function openDialog(event) {
		if(href.startsWith("#")) return;
		
		event.preventDefault();
		event.stopPropagation();
		
		if(!isCorrectLink(href)) return;
		
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

{#if isCorrectLink(href) || href.startsWith("#")}
<a
	class="linkElement"
	href={href}
    on:click={openDialog}
    {title}
>
    {@render children?.()}
</a>
<Dialog headline="External link" bind:open>
	Are you sure you want to open this link?<br>
	<code class="linkPreview">
		{href}
	</code>
	{#snippet buttons()}
		<Button variant="filled">Go back</Button>
		<Button variant="tonal" onclick={() => openLink(href)}>Open</Button>
	{/snippet}
</Dialog>
{:else}
	<a class="noLink">{@render children?.()}</a>
{/if}

<style>
	a.linkElement {
		cursor: pointer;
		color: var(--m3c-primary);
		font-weight: 500;
		
		transition: color var(--m3-easing-fast);
	}
	
	a.linkElement:hover {
		color: var(--m3c-on-primary-container);
	}
	
	.linkPreview {
		display: flex;
		
		padding: .5rem .7rem;
		margin-top: .5rem;
		font-size: .9rem;
		
		max-width: 100%;
		
		overflow-wrap: anywhere;
	}
</style>