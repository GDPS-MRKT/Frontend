<script>
	import TagsGroup from "./TagsGroup.svelte";
	import Tag from "./Tag.svelte";
	
	let { children, icon } = $props();
	
	let show = $state(false);
</script>

<div class="menuGroup" show={show}>
	<TagsGroup>
		<Tag icon={icon} onClick={() => show = !show} />
	</TagsGroup>
	
	{@render children()}
</div>

<style>
	.menuGroup {
		display: flex;
		flex-direction: column;
		position: relative;
		
		gap: 5px;
		transition: var(--m3-easing-fast);
		margin-left: auto;
		margin-bottom: auto;
		
		opacity: 0;
	}
	
	:global .containsMenu:hover .menuGroup {
		opacity: 1;
	}
</style>