<script>
	import { Icon } from "m3-svelte";
	
	let { icon, label, color, title, onClick } = $props();
</script>

<div class={["tag", (color != undefined ? color : ""), (onClick != undefined ? "m3-layer clickable" : "")].join(" ")} title={title != undefined ? title : ""} on:click={onClick}>
	{#if icon != undefined}
		<Icon icon={icon} />
	{/if}
	
	{#if label != undefined}
		<span>{label}</span>
	{/if}
</div>

<style>
	.tag {
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
	}
	
	.tag.clickable {
		user-select: none;
		
		box-shadow: none;
		cursor: pointer;
		
		transition:
			border-radius var(--m3-easing-fast-spatial),
			box-shadow var(--m3-easing-fast),
			background-color var(--m3-easing-fast),
			color var(--m3-easing-fast);
	}
	
	.tag.clickable:hover {
		box-shadow: var(--m3-elevation-1);
	}
	
	.tag.clickable:active {
		--shape: var(--m3-shape-small);
	}
	
	.tag.gold {
		background: var(--m3c-primary-container-gold);
		color: var(--m3c-on-primary-container-gold);
	}
	
	.tag.primary {
		background: var(--m3c-primary);
		color: var(--m3c-on-primary);
	}
	
	:global .tag span {
		font-size: 0.875rem;
		font-weight: 500;
	}
	
	.tag:nth-of-type(1) {
		border-top-left-radius: var(--m3-shape-large);
		border-bottom-left-radius: var(--m3-shape-large);
	}
	
	.tag:nth-last-of-type(1) {
		border-top-right-radius: var(--m3-shape-large);
		border-bottom-right-radius: var(--m3-shape-large);
	}
	
	:global .small .tag {
		gap: 3px;
		
		font-size: 16px;
		padding: .15rem .3rem;
		
		--shape: var(--m3-shape-small);
		border-radius: var(--shape);
	}
	
	:global .small .tag span {
		font-size: 13px;
	}
	
	:global .small .tag:nth-of-type(1) {
		border-top-left-radius: var(--m3-shape-medium);
		border-bottom-left-radius: var(--m3-shape-medium);
	}
	
	:global .small .tag:nth-last-of-type(1) {
		border-top-right-radius: var(--m3-shape-medium);
		border-bottom-right-radius: var(--m3-shape-medium);
	}
	
	:global .small .tag.clickable {
		cursor: pointer;
		
		transition:
			border-radius var(--m3-easing-fast-spatial),
			box-shadow var(--m3-easing-fast),
			background-color var(--m3-easing-fast),
			color var(--m3-easing-fast);
	}
	
	:global .small .tag.clickable:active {
		--shape: var(--m3-shape-extra-small);
	}
</style>