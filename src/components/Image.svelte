<script>
	import { LoadingIndicator } from "m3-svelte";
	
	let { src, alt, title, loading = "center" } = $props();
	
	var mainImageLoaded = $state(false);
	var altImageLoaded = $state(false);
</script>

<object class={[loading, (mainImageLoaded || altImageLoaded ? "loaded" : "")].join(" ")} {title}>
	<span class="loading">
		<LoadingIndicator class="loadingIndicator" center={false} size={24} />
	</span>
	
	<img class={["mainImage", (mainImageLoaded ? "loaded" : "")].join(" ")} src={src} on:load={() => mainImageLoaded = true} />
	
	{#if alt != undefined}
		<img class={["altImage", (!mainImageLoaded && altImageLoaded ? "loaded" : "")].join(" ")} src={alt} on:load={() => altImageLoaded = true} />
	{/if}
</object>

<style>
	object, img {
		display: flex;
		
		width: 100%;
		height: 100%;
		
		object-fit: cover;
	}
	
	object {
		background: var(--m3c-surface-container);
		position: relative;
	}
	
	img {
		display: none;
	}
	
	img.mainImage {
		z-index: 1;
	}
	
	img.altImage {
		z-index: 0;
	}
	
	img.mainImage.loaded,
	img.altImage.loaded {
		display: initial;
	}
	
	:global object .loading {
		display: flex;
		justify-content: center;
		
		width: 100%;
		height: 100%;
	}
	
	:global object:not(.center) .loading {
		padding: .75rem;
	}
	
	:global object.center .loading {
		align-items: center;
	}
	
	:global object.left .loading {
		justify-content: flex-start;
	}
	
	:global object.right .loading {
		justify-content: flex-end;
	}
	
	:global object .loading .loadingIndicator {
		max-width: 65%;
		max-height: 65%;
	}
	
	:global .loaded .loading {
		display: none;
	}
</style>