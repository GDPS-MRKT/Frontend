<script>
	import "./+layout.css";
	import { beforeNavigate, onNavigate, afterNavigate } from '$app/navigation';
	import { LoadingIndicator } from "m3-svelte";
	import Sidebar from "../components/Sidebar.svelte";
	
	beforeNavigate(() => {
		pageLoaderTimeout = setTimeout(() => firstPageLoad = false, 200);
	});
	
	onNavigate((navigation) => {
		if(!document.startViewTransition) return;
		
		return new Promise((resolve) => {
			document.startViewTransition(async () => {
				resolve();
				await navigation.complete;
			});
		});
	});
	
	afterNavigate(() => {
		firstPageLoad = true;
		clearTimeout(pageLoaderTimeout);
	});

	let { children } = $props();
	let firstPageLoad = $state(false);
	let pageLoaderTimeout = $state(null);
</script>

<svelte:head>
	<title>MRKT — Yet another GDPS marketplace.</title>
</svelte:head>

<div class="body">
	<div class={["pageLoader", (firstPageLoad ? "loaded" : "")].join(" ")}>
		<LoadingIndicator size={96} />
	</div>
	
	<Sidebar />
	
	<div class="pageBody">
		{@render children()}
	</div>
</div>

<style>
	.pageLoader {
		display: flex;
		justify-content: center;
		align-items: center;
		
		background: var(--m3v-background);
		
		width: 100vw;
		height: 100vh;
		
		position: fixed;
		z-index: 10;
		
		transition: var(--m3-easing-fast);
	}
	
	.pageLoader.loaded {
		opacity: 0;
		visibility: hidden;
	}
</style>