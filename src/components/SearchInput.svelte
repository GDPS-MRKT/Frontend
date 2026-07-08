<script>
	import { Icon } from "m3-svelte";
	
	import iconSearch from "@ktibow/iconset-material-symbols/search-rounded";
	
	let { onInput } = $props();
</script>

<div class="searchInputElement">
	<input type="text" placeholder="Type GDPS name..." on:input={(event) => onInput(event.target.value)} />
	<span class="searchIcon">
		<Icon icon={iconSearch} />
	</span>
</div>

<style>
	.searchInputElement {
		display: flex;
		align-items: center;
		justify-content: flex-end;
		
		background: var(--m3c-surface-container-highest);
		border-radius: var(--m3-shape-extra-large);
		
		width: 100%;
		
		position: relative;
	}
	
	.searchIcon {
		font-size: 30px;
		width: 30px;
		height: 30px;
		
		margin-right: 1rem;
		color: var(--m3c-on-primary-container);
		
		position: absolute;
	}
	
	input {
		font-size: 20px;
		
		background: none;
		border: none;
		
		padding: 1rem;
		border-radius: var(--m3-shape-extra-large);
		color: var(--m3c-on-primary-container);
		
		width: 100%;
	}
	
	input:focus {
		outline: none;
	}
</style>