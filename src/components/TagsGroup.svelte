<script>
	let { children, size } = $props();
</script>

<div class={["tagsGroup", (size != undefined ? size : "")].join(" ")}>
	{@render children()}
</div>

<style>
	.tagsGroup {
		display: flex;
		flex-direction: row;
		
		gap: 5px;
	}
	
	:global .tagsGroup.small {
		gap: 3px;
	}
</style>