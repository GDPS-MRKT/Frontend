<script>
	let { children, wrap, size } = $props();
	import ConnectedElements from './ConnectedElements.svelte';
</script>

<div class={["tagsGroup", (wrap != undefined ? wrap : ""), (size != undefined ? size : "")].join(" ")} role="region">
	<ConnectedElements side="horisontal" size={(size == "small" ? "medium" : "large")}>
		{@render children()}
	</ConnectedElements>
</div>

<style>
	.tagsGroup {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		
		gap: 2px;
		
		overflow-x: scroll;
	}
	
	:global .tagsGroup.small {
		gap: 1px;
	}
	
	:global .tagsGroup.nowrap {
		flex-wrap: nowrap;
	}

	.tagsGroup::-webkit-scrollbar {
		width: 0px;
		height: 0px;
	}
</style>