<script>
	import { Icon, Button, LoadingIndicator } from "m3-svelte";
	import GDPS from "../../components/GDPS.svelte";
	import SearchInput from "../../components/SearchInput.svelte";
	
	import iconStar from "@ktibow/iconset-material-symbols/star-rounded";
	import iconStarOutline from "@ktibow/iconset-material-symbols/star-outline-rounded";
	import iconRocketLaunch from "@ktibow/iconset-material-symbols/rocket-launch-rounded";
	import iconRocketLaunchOutline from "@ktibow/iconset-material-symbols/rocket-launch-outline-rounded";
	import iconSchedule from "@ktibow/iconset-material-symbols/schedule-rounded";
	import iconScheduleOutline from "@ktibow/iconset-material-symbols/schedule-outline-rounded";
	import iconQuestionMark from "@ktibow/iconset-material-symbols/question-mark-rounded";
	
	var selectedTab = $state("recommendations");
	
	let searchTabs = $state({
		recommendations: {id: "recommendations", text: "Recommendations", icon: iconStarOutline, iconSelected: iconStar, path: "/"},
		popular: {id: "popular", text: "Popular", icon: iconRocketLaunchOutline, iconSelected: iconRocketLaunch, path: "/"},
		new: {id: "new", text: "New", icon: iconScheduleOutline, iconSelected: iconSchedule, path: "/"},
	});
	const searchTabsIDs = Object.keys(searchTabs);
	
	let gdpss = $state({search: false});
	
	for(let i = 0; i < searchTabsIDs.length; i++) {
		gdpss[searchTabsIDs[i]] = [];
	}
	// Obv test data
	gdpss.recommendations.push("123");
	gdpss.recommendations.push("123");
	gdpss.recommendations.push("123");
	gdpss.recommendations.push("123");
	gdpss.recommendations.push("123");
	
	gdpss.new.push("123");
	gdpss.new.push("123");
	
	function changeSearchTab(tabID) {
		selectedTab = tabID;
		searchTabs = searchTabs;
	}
	
	function searchGDPSs(value) {
		changeSearchTab(value.length ? "search" : "recommendations");
		console.log(value);
	}
</script>

<div class="searchDiv">
	<div class="searchInputDiv">
		<h1>Search GDPSs</h1>
	</div>
	
	<div class="searchElementsDiv">
		<div class="searchStickyDiv">
			<SearchInput onInput={(event) => searchGDPSs(event)} />
			
			<div class="buttonsDiv">
				{#each Object.values(searchTabs) as tab}
					<Button variant={selectedTab == tab.id ? "filled" : "tonal"} iconType="left" onclick={() => changeSearchTab(tab.id)}>
						<Icon icon={selectedTab == tab.id ? tab.iconSelected : tab.icon} /> {tab.text}
					</Button>
				{/each}
			</div>
		</div>
		
		<div class="elementsDiv">
			{#if gdpss[selectedTab] !== false}
				{#if Object.values(gdpss[selectedTab]).length}
					{#each Object.values(gdpss[selectedTab]) as gdps}
						<GDPS />
					{/each}
				{:else}
					<div class="errorDiv">
						<h1><Icon icon={iconQuestionMark} /></h1>
						<h2>Nothing found.</h2>
					</div>
				{/if}
			{:else}
				<LoadingIndicator size={70} />
			{/if}
		</div>
	</div>
</div>

<style>
	.searchDiv {
		display: flex;
		flex-direction: column;
		
		width: 100%;
		min-width: 100%;
	}
	
	.searchInputDiv {
		display: flex;
		flex-direction: column;
		align-items: center;
		
		gap: 5px;
		width: 100%;
	}
	
	.searchStickyDiv {
		display: flex;
		flex-direction: column;
		align-items: center;
		
		padding: 10px;
		background: light-dark(#ffffffc0, #121212c0);
		border-radius: calc(var(--m3-shape-extra-large) + 10px);
		
		gap: 10px;
		width: 50%;
		
		top: -30px;
		position: sticky;
		
		z-index: 3;
	}
	
	.buttonsDiv {
		display: flex;
		flex-direction: row;
		gap: 5px;
		
		width: max-content;
	}
	
	.searchElementsDiv {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		
		max-width: 100%;
		gap: 10px;
	}
	
	.elementsDiv {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		
		max-width: 100%;
		min-height: 350px;
		gap: 10px;
	}
	
	.errorDiv {
		display: flex;
		flex-direction: column;
		justify-content: center;
		
		background: var(--m3c-surface-container-highest);
		color: var(--m3c-on-primary-container);
		
		padding: 1rem;
		border-radius: var(--m3-shape-extra-large);
		
		height: max-content;
	}
	
	.errorDiv h1 {
		text-align: center;
	}
	
	.errorDiv h2 {
		margin: 0px;
		font-size: 30px;
	}
	
	h1 {
		font-size: 50px;
		color: var(--m3c-on-primary-container);
	}
</style>