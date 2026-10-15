<script>
	import { Dialog, Button, TextField, ConnectedButtons } from "m3-svelte";
	import TagsGroup from "../TagsGroup.svelte";
	import Tag from "../Tag.svelte";
	import Markdown from "../Markdown.svelte";
	
	let { id, value, title, description, button, onClose, open = $bindable(), onUpdate, required = true } = $props();
	
	let inputValue = $state(value);
	
	let markdownPreviewMode = $state(0);
	
	let dialogOnClose = function(event) {
		inputValue = value;
		changePreviewMode(0);
	}
	
	let dialogOnInput = function(event) {
		inputValue = event.target.value;
	}
	
	let dialogOnUpdate = function(newValue) {
		onUpdate(newValue.trim());
		
		inputValue = value = newValue.trim();
		open = false;
		changePreviewMode(0);
	}
	
	let changePreviewMode = function(previewModeValue) {
		markdownPreviewMode = previewModeValue;
	}
</script>

<input type="hidden" name={id} value={inputValue} />
<Dialog headline={title} closedby="closerequest" onclose={onClose} ontoggle={dialogOnClose} bind:open>
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
	
	<ConnectedButtons>
		<Button variant="tonal" square onclick={() => changePreviewMode(0)}>
			<input type="radio" checked={markdownPreviewMode == 0} name="markdownPreview" />
			Edit
		</Button>
		<Button variant="tonal" square onclick={() => changePreviewMode(1)}>
			<input type="radio" checked={markdownPreviewMode == 1} name="markdownPreview" />
			Preview
		</Button>
	</ConnectedButtons>
	
	{#if markdownPreviewMode == 0}
		<textarea class="markdownEditor" placeholder="Description..." oninput={dialogOnInput} bind:value={inputValue} />
	{:else}
		<div class="markdownElement">
			<Markdown source={inputValue} />
		</div>
	{/if}
	
	{#snippet buttons()}
		<Button variant="text">Cancel</Button>
		<Button variant="filled" onclick={() => dialogOnUpdate(inputValue)}>{button}</Button>
	{/snippet}
</Dialog>

<style>
	.markdownElement {
		display: flex;
		flex-direction: column;
		gap: 10px;
		
		border-radius: 10px;
		padding: 10px;
		
		height: 60vh;
		width: 70vw;
		max-height: 100%;
		max-width: 100%;
		
		background-color: var(--m3c-surface-container-highest);
		color: var(--m3c-on-surface);
		
		overflow: auto;
		overflow-x: hidden;
		overflow-wrap: break-word;
	}
	
	.markdownEditor {
		font-size: 0.875rem;
		
		border-radius: 10px;
		padding: 10px;
		
		height: 60vh;
		width: 70vw;
		max-height: 100%;
		max-width: 100%;
		
		background-color: var(--m3c-surface-container-highest);
		border: none;
		color: var(--m3c-on-surface);
		
		resize: none;
	}
	
	:global dialog {
		max-width: 50vw !important;
	}
</style>