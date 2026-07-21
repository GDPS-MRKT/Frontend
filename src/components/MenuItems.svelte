<script>
	let { children } = $props();
</script>

<div class="menuItems">
	{@render children()}
</div>

<style>
	.menuItems {
		display: flex;
		flex-direction: column;
		
		gap: 2px;
		
		position: absolute;
		top: calc(100% + 5px);
		right: 0px;
		
		width: max-content;
		
		opacity: 0;
		visibility: hidden;
		transition: var(--m3-easing-fast);
	}
	
	:global .menuGroup[show=true] .menuItems {
		opacity: 1;
		visibility: initial;
		
		top: calc(100% + 10px);
	}
</style>