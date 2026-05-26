<script>
	import { Icon } from "m3-svelte";
	
	let { icon, label } = $props();
</script>

<h2 class="tag">
	{#if icon != undefined}
		<Icon icon={icon} />
	{/if}
	<text>{label}</text>
</h2>

<style>
	h2 {
		display: flex;
		gap: 5px;
		
		margin: 0px;
		
		font-size: 24px;
		font-weight: 400;
		
		background: var(--m3c-secondary-container);
		color: var(--m3c-on-secondary-container);
		padding: .5rem;
		
		border-radius: var(--m3-shape-small);
		
		height: 40px;
	}
	
	:global h2 text {
		font-size: 18px;
	}
	
	h2:nth-of-type(1) {
		border-top-left-radius: var(--m3-shape-large);
		border-bottom-left-radius: var(--m3-shape-large);
	}
	
	h2:nth-last-of-type(1) {
		border-top-right-radius: var(--m3-shape-large);
		border-bottom-right-radius: var(--m3-shape-large);
	}
	
	:global .small h2 {
		gap: 3px;
		
		font-size: 16px;
		padding: .15rem .3rem;
		
		height: 21px;
		
		border-radius: var(--m3-shape-extra-small);
	}
	
	:global .small h2 text {
		font-size: 13px;
	}
	
	:global .small h2:nth-of-type(1) {
		border-top-left-radius: var(--m3-shape-small);
		border-bottom-left-radius: var(--m3-shape-small);
	}
	
	:global .small h2:nth-last-of-type(1) {
		border-top-right-radius: var(--m3-shape-small);
		border-bottom-right-radius: var(--m3-shape-small);
	}
</style>