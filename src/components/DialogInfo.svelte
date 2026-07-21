<script>
	import { Dialog, Button } from "m3-svelte";
	
	let { title, description, button, open = $bindable() } = $props();
</script>

<Dialog headline={title} bind:open>
	{#if typeof description != "string"}
		{#each description as descriptionPart, index}
			{#if index}
				<br>
			{/if}
			{descriptionPart}
		{/each}
	{:else}
		{description}
	{/if}
	{#snippet buttons()}
		<Button variant="filled">{button}</Button>
	{/snippet}
</Dialog>