<script>
	let { children, size } = $props();
</script>

<div class={["tagsGroup draggable", (size != undefined ? size : "")].join(" ")} role="region">
	{@render children()}
</div>

<style>
	.tagsGroup {
		display: flex;
		flex-direction: row;
		
		gap: 5px;
		
		overflow-x: scroll;
	}
	
	:global .tagsGroup.small {
		gap: 3px;
	}
</style>