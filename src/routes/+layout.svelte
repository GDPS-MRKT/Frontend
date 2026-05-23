<script>
	import "./+layout.css";
	import Sidebar from "../components/Sidebar.svelte";

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