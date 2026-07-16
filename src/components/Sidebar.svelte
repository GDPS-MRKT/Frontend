<script>
	import { goto } from '$app/navigation';
	import { page } from '$app/stores';
	import { NavCMLX, NavCMLXItem } from "m3-svelte";
	
	import iconHome from "@ktibow/iconset-material-symbols/home-rounded";
	import iconHomeOutline from "@ktibow/iconset-material-symbols/home-outline-rounded";
	import iconSearch from "@ktibow/iconset-material-symbols/search-rounded";
	import iconPerson from "@ktibow/iconset-material-symbols/person-rounded";
	import iconPersonOutline from "@ktibow/iconset-material-symbols/person-outline-rounded";
	
	function isPageSelected(path) {
		return path == $page.url.pathname;
	}
	
	const tabs = [
		{text: "Home", icon: iconHomeOutline, iconSelected: iconHome, path: "/"},
		{text: "Search", icon: iconSearch, iconSelected: iconSearch, path: "/search"},
		{text: "Profile", icon: iconPersonOutline, iconSelected: iconPerson, path: "/profile/Sa1ntSosetHui"}
	];
</script>

<div class="sidebar">
	<NavCMLX variant="auto">
		{#each tabs as tab}
			<NavCMLXItem
				variant="auto"
				icon={isPageSelected(tab.path) ? tab.iconSelected : tab.icon}
				text={tab.text}
				selected={isPageSelected(tab.path)}
				onclick={() => (typeof tab.onclick != "undefined" ? tab.onclick() : goto(tab.path))}
			/>
		{/each}
	</NavCMLX>
</div>

<style>
	.sidebar {
		display: flex;
		align-items: center;
		justify-content: center;
		
		view-transition-name: header;
	}
	
	@media (width < 52.5rem) {
		.sidebar {
			position: fixed;
			bottom: 0px;
			width: 100%;
			
			z-index: 3;
		}
		
		:global .sidebar > nav {
			width: 100%;
		}
	}
</style>