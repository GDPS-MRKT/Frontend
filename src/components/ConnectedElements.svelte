<script>
	let { children, side = 'vertical', size = 'extra-large' } = $props();
</script>

<div class={["connectedElements", size, side].join(" ")} role="region">
	{@render children()}
</div>

<style>
	.connectedElements {
		display: contents;
		
		--shape-outside: var(--m3-shape-extra-large);
		--shape-inside: var(--m3-shape-large);
	}
	
	:global .connectedElements .connectedElement {
		border-radius: var(--shape-inside);
		--shape: var(--shape-inside);
	}
	
	:global .connectedElements .connectedElement.clickable:active {
		border-radius: var(--shape) !important;
	}
	
	:global .connectedElements.vertical > .connectedElement:nth-of-type(1) {
		border-top-left-radius: var(--shape-outside);
		border-top-right-radius: var(--shape-outside);
	}
	
	:global .connectedElements.vertical > .connectedElement:nth-last-of-type(1) {
		border-bottom-left-radius: var(--shape-outside);
		border-bottom-right-radius: var(--shape-outside);
	}
	
	:global .connectedElements.horisontal > .connectedElement:nth-of-type(1) {
		border-top-left-radius: var(--shape-outside);
		border-bottom-left-radius: var(--shape-outside);
	}
	
	:global .connectedElements.horisontal > .connectedElement:nth-last-of-type(1) {
		border-top-right-radius: var(--shape-outside);
		border-bottom-right-radius: var(--shape-outside);
	}
	
	:global .connectedElements.extra-large {
		--shape-outside: var(--m3-shape-extra-large);
		--shape-inside: var(--m3-shape-large);
	}
	
	:global .connectedElements.large-increased {
		--shape-outside: var(--m3-shape-large-increased);
		--shape-inside: var(--m3-shape-small);
	}
	
	:global .connectedElements.large-increased .clickable {
		--shape-outside: var(--m3-shape-large-increased);
		--shape-inside: var(--m3-shape-medium);
	}
	
	:global .connectedElements.large {
		--shape-outside: var(--m3-shape-large);
		--shape-inside: var(--m3-shape-medium);
	}
	
	:global .connectedElements.medium {
		--shape-outside: var(--m3-shape-medium);
		--shape-inside: var(--m3-shape-small);
	}
	
	:global .connectedElements.small {
		--shape-outside: var(--m3-shape-small);
		--shape-inside: var(--m3-shape-extra-small);
	}
</style>