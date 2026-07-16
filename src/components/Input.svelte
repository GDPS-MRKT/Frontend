<script>
	import { Icon } from "m3-svelte";
	import Image from "./Image.svelte";
	
	import iconSend from "@ktibow/iconset-material-symbols/send-rounded";
	
	let { image, label, onInput } = $props();
</script>

<div class="searchInputElement">
	<span class="inputLogo">
		<Image src={image} title="Logo" />
	</span>
	
	<input type="text" placeholder={label} on:input={(event) => onInput(event.target.value)} />
	
	<div type="button" class="m3-layer sendButton">
		<Icon icon={iconSend} />
	</div>
</div>

<style>
	.searchInputElement {
		display: flex;
		align-items: center;
		justify-content: flex-end;
		
		width: 100%;
		
		gap: 2px;
		
		position: relative;
	}
	
	.sendButton {
		display: flex;
		align-items: center;
		
		gap: 5px;
		
		margin: 0px;
		padding: .5rem;
		
		font-size: 1.25rem;
		font-weight: 400;
		
		background: var(--m3c-primary);
		color: var(--m3c-on-primary);
		
		--shape: var(--m3-shape-medium);
		border-radius: var(--shape);
		border-top-right-radius: var(--m3-shape-large);
		border-bottom-right-radius: var(--m3-shape-large);
		
		cursor: pointer;
		user-select: none;
		box-shadow: none;
		
		transition:
			border-radius var(--m3-easing-fast-spatial),
			box-shadow var(--m3-easing-fast),
			background-color var(--m3-easing-fast),
			color var(--m3-easing-fast);
	}
	
	.sendButton:active {
		--shape: var(--m3-shape-small);
	}
	
	input {
		font-size: 1rem;
		
		background: none;
		border: none;
		
		padding: .5rem;
		
		background: var(--m3c-secondary-container);
		
		border-radius: var(--m3-shape-large);
		border-top-right-radius: var(--m3-shape-medium);
		border-bottom-right-radius: var(--m3-shape-medium);
		
		color: var(--m3c-on-primary-container);
		
		width: 100%;
	}
	
	input:focus {
		outline: none;
	}
	
	.inputLogo {
		min-width: 36px;
		max-height: 36px;
		max-width: 36px;
		
		border-radius: 100px;
		overflow: hidden;
		
		margin-right: 3px;
	}
</style>