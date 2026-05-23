<script>
	import { NavigationRail, NavigationRailItem } from "m3-svelte";
	import iconHome from "@ktibow/iconset-material-symbols/home-rounded";
	import iconSearch from "@ktibow/iconset-material-symbols/search-rounded";
</script>

<NavigationRail>
	<NavigationRailItem
		icon={iconHome}
		label="Home"
		id="home"
	/>
	<NavigationRailItem
		icon={iconSearch}
		label="Search"
		id="search"
	/>
</NavigationRail>