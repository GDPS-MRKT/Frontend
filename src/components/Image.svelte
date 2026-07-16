<script>
	let { src, alt, title } = $props();
</script>

<object data={src} {title}>
	{#if alt != undefined}
		<img src={alt} />
	{/if}
</object>

<style>
	object, img {
		width: 100%;
		height: 100%;
		
		object-fit: cover;
	}
</style>