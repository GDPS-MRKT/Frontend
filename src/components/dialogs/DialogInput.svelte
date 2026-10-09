<script>
	import { Dialog, Button, TextField } from "m3-svelte";
	
	let { id, value, title, description, button, open = $bindable(), onUpdate, required = true } = $props();
	
	let inputError = $state(false);
	let inputValue = $state(value);
	
	let dialogOnKeyboard = function(event) {
		if(event.keyCode == 13) dialogOnUpdate(event.target.value);
	}
	
	let dialogOnClose = function(event) {
		value = inputValue;
		inputError = false;
	}
	
	let dialogOnInput = function(event) {
		const inputValue = event.target.value;
		
		if(!inputValue.trim().length && required) inputError = true;
		else inputError = false;
	}
	
	let dialogOnUpdate = function(newValue) {
		if(inputError) return;
		
		onUpdate(newValue.trim());
		inputValue = newValue;
		open = false;
	}
</script>

<input type="hidden" name={id} value={inputValue} />
<Dialog headline={title} closedby="closerequest" ontoggle={dialogOnClose} bind:open>
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
	
	<TextField label={title} required={required} error={inputError} oninput={dialogOnInput} onkeyup={dialogOnKeyboard} bind:value={value} />
	
	{#snippet buttons()}
		<Button variant="text">Cancel</Button>
		<Button variant="filled" onclick={() => dialogOnUpdate(value)}>{button}</Button>
	{/snippet}
</Dialog>

<style>
	:global dialog .content {
		display: flex;
		flex-direction: column;
		gap: 10px;
	}
	
	:global dialog div input,
	:global dialog div .layer {
		border-radius: 10px !important;
	}
	
	:global dialog div .layer::after {
		border-radius: 10px !important;
		height: 100% !important;
		
		background-color: transparent !important;
		border-bottom: 1px solid var(--error, var(--m3c-on-surface-variant));
	}
	
	:global dialog div:has(input:focus) .layer::after {
		border-bottom: 2px solid var(--error, var(--m3c-primary));	
	}
</style>