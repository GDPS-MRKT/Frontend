<script>
	import "./+layout.css";
	import { onNavigate } from '$app/navigation';
	import Sidebar from "../components/Sidebar.svelte";
	
	onNavigate((navigation) => {
		if(!document.startViewTransition) return;
		
		return new Promise((resolve) => {
			document.startViewTransition(async () => {
				resolve();
				await navigation.complete;
			});
		});
	});

	let { children } = $props();
</script>

<svelte:head>
	<title>MRKT — Yet another GDPS marketplace.</title>
</svelte:head>

<div class="body">
	<Sidebar />
	
	<div class="pageBody">
		{@render children()}
	</div>
</div>