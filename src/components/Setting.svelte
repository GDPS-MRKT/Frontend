<script>
	import { goto } from '$app/navigation';
	import { Icon, Button } from "m3-svelte";
	import Image from "./Image.svelte";
	
	let { icon, title, value, children } = $props();
</script>

<div class="setting">
	<div class="settingTitle">
		<span class="settingIcon">
			{#if typeof icon != "function"}
				<Icon icon={icon} />
			{:else}
				<svelte:component this={icon} />
			{/if}
		</span>
		
		<div class="gdpsName">
			<h1>{title}</h1>
			<h3>{value}</h3>
		</div>
	</div>
	
	{#if children != undefined}
		<div class="settingButton">
			{@render children()}
		</div>
	{/if}
</div>

<style>
	.setting {
		display: flex;
		justify-content: space-between;
		
		background: var(--m3c-surface-container-highest);
		
		padding: .75rem;
		--shape: var(--m3-shape-small);
		border-radius: var(--shape);
		
		transition:
			border-radius var(--m3-easing-fast-spatial),
			box-shadow var(--m3-easing-fast),
			background-color var(--m3-easing-fast),
			color var(--m3-easing-fast);
	}
	
	.setting:nth-of-type(1) {
		border-top-left-radius: var(--m3-shape-large-increased);
		border-top-right-radius: var(--m3-shape-large-increased);
	}
	
	.setting:nth-last-of-type(1) {
		border-bottom-left-radius: var(--m3-shape-large-increased);
		border-bottom-right-radius: var(--m3-shape-large-increased);
	}
	
	.settingTitle {
		display: flex;
		align-items: center;
		
		gap: 7px;
	}
	
	.settingTitle h1 {
		font-size: 1.2rem;
		color: var(--m3c-on-primary-container);
	}
	
	.settingTitle h3 {
		font-weight: 400;
		font-size: 14px;
		margin: 0px;
		
		color: var(--m3c-on-secondary-container);
	}
	
	.settingTitle .settingIcon {
		display: flex;
		align-items: center;
		justify-content: center;
		
		height: 40px;
		width: 40px;	
		padding: .5rem;
		
		font-size: 25px;
		
		border-radius: var(--m3-shape-small);
		background: var(--m3c-secondary-container);
		overflow: hidden;
	}
</style>