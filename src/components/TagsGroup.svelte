<script>
	let { children, size } = $props();
</script>

<div class={["tagsGroup", (size != undefined ? size : "")].join(" ")} role="region">
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

	.tagsGroup::-webkit-scrollbar {
		width: 0px;
		height: 0px;
	}
</style>