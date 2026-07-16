<script>
	import { Icon } from "m3-svelte";
	
	let { icon, label, color, title, onClick } = $props();
</script>

<div class={["menu primary", (color != undefined ? color : ""), (onClick != undefined ? "m3-layer clickable" : "")].join(" ")} title={title != undefined ? title : ""} on:click={onClick}>
	{#if icon != undefined}
		<Icon icon={icon} />
	{/if}
	
	{#if label != undefined}
		<span>{label}</span>
	{/if}
</div>

<style>
	.menu {
		display: flex;
		align-items: center;
		
		gap: 5px;
		
		margin: 0px;
		padding: .5rem;
		
		font-size: 1.25rem;
		font-weight: 400;
		
		background: light-dark(var(--m3c-tertiary-container), var(--m3c-secondary-container));
		color: light-dark(var(--m3c-on-tertiary-container), var(--m3c-on-secondary-container));
		
		--shape: var(--m3-shape-medium);
		border-radius: var(--shape);
		
		overflow-wrap: none;
	}
	
	.menu.clickable {
		user-select: none;
		
		box-shadow: none;
		cursor: pointer;
		
		transition:
			border-radius var(--m3-easing-fast-spatial),
			box-shadow var(--m3-easing-fast),
			background-color var(--m3-easing-fast),
			color var(--m3-easing-fast);
	}
	
	.menu.clickable:hover {
		box-shadow: var(--m3-elevation-1);
	}
	
	.menu.clickable:active {
		--shape: var(--m3-shape-small);
	}
	
	.menu:nth-of-type(1) {
		border-top-left-radius: var(--m3-shape-large);
		border-top-right-radius: var(--m3-shape-large);
	}
	
	.menu:nth-last-of-type(1) {
		border-bottom-left-radius: var(--m3-shape-large);
		border-bottom-right-radius: var(--m3-shape-large);
	}
	
	.menu.gold {
		background: var(--m3c-primary-container-gold);
		color: var(--m3c-on-primary-container-gold);
	}
	
	.menu.primary {
		background: var(--m3c-primary);
		color: var(--m3c-on-primary);
	}
	
	:global .menu span {
		font-size: 0.875rem;
		font-weight: 500;
	}
</style>