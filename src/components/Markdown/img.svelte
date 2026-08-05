<script>
	import { Dialog, Button } from "m3-svelte";
	import Image from "../Image.svelte";
	
    let { href = '', title = undefined } = $props();
	
	href = "https://gdpshub-image-proxy.m336.workers.dev/" + encodeURIComponent(href); // Link will be changed to MRKT exclusive later
</script>

<Image src={href} title={title} />