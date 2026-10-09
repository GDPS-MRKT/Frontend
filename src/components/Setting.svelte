<script>
	import { goto } from '$app/navigation';
	import { Icon, Button } from "m3-svelte";
	import Image from "./Image.svelte";
	import DialogInfo from "./dialogs/DialogInfo.svelte";
	import DialogInput from "./dialogs/DialogInput.svelte";
	
	import iconEdit from "@ktibow/iconset-material-symbols/edit-rounded";
	import iconInfo from "@ktibow/iconset-material-symbols/info-i-rounded";
	
	let { icon, id, title, value, type = 'info', description = '', required = true } = $props();
	
	let settingValue = $state(value);
	let dialogOpened = $state(false);
	let dialogOnUpdate = function(newValue) {
		settingValue = newValue;
	}
</script>

<div class="setting connectedElement">
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
			<h3>{settingValue.length ? settingValue : "Unset"}</h3>
		</div>
	</div>
	
	<div class="settingButton">
		<Button variant={type == "info" ? "tonal" : "filled"} iconType="full" onclick={() => dialogOpened = !dialogOpened}>
			<Icon icon={type == "info" ? iconInfo : iconEdit} />
		</Button>
		
		{#if type == "info"}
			<DialogInfo
				title={title}
				description={description}
				button="OK"
				open={dialogOpened}
			/>
		{:else}
			<DialogInput
				id={id}
				value={value}
				title={title}
				description={description}
				button="Save"
				open={dialogOpened}
				onUpdate={dialogOnUpdate}
				required={required}
			/>
		{/if}
	</div>
</div>

<style>
	.setting {
		display: flex;
		justify-content: space-between;
		
		background: var(--m3c-surface-container-highest);
		
		padding: .75rem;
		gap: 10px;
		
		transition:
			border-radius var(--m3-easing-fast-spatial),
			box-shadow var(--m3-easing-fast),
			background-color var(--m3-easing-fast),
			color var(--m3-easing-fast);
	}
	
	.settingTitle {
		display: flex;
		align-items: center;
		
		gap: 7px;
		
		width: 100%;
	}
	
	.settingTitle h1 {
		font-size: 14px;
		color: var(--m3c-on-primary-container);
	}
	
	.settingTitle h3 {
		font-weight: 400;
		font-size: 1rem;
		margin: 0px;
		
		color: var(--m3c-on-secondary-container);
		
		width: 0px;
		min-width: 100%;
		white-space: nowrap;
		
		overflow: hidden;
		text-overflow: ellipsis;
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
	
	.gdpsName {
		width: 100%;
	}
</style>