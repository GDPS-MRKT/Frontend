<script>
	import { goto } from '$app/navigation';
	import { Icon, Button } from "m3-svelte";
	import TagsGroup from "./TagsGroup.svelte";
	import Tag from "./Tag.svelte";
	
	import iconPerson from "@ktibow/iconset-material-symbols/person-rounded";
	import iconVisibility from "@ktibow/iconset-material-symbols/visibility-rounded";
	import iconStar from "@ktibow/iconset-material-symbols/star-rounded";
	import iconFavorite from "@ktibow/iconset-material-symbols/favorite-rounded";
	import iconHistory from "@ktibow/iconset-material-symbols/history-rounded";
</script>

<div class="m3-layer container gdps">
	<div class="bannerDiv">
		<img class="banner" src="https://images.gcs.skin/gcs/banner.png" alt="GDPS banner" />
	</div>
	
	<div class="gdpsDesc">
		<div class="gdpsTitle">
			<span class="logo">
				<img src="https://images.gcs.skin/gcs/logo.png" alt="GDPS logo" />
			</span>
			
			<div class="gdpsName">
				<h1>GreenCatsServer</h1>
				<h3 on:click={() => goto("/profile/Sa1ntSosetHui")}>Sa1ntSosetHui</h3>
			</div>
		</div>
		
		<TagsGroup size="small">
			<Tag icon={iconStar} color="gold" label="Recommended" />
			<Tag label="2.2" />
			<Tag label="GCS" />
			<Tag label="Femboys" />
			<Tag label="Furi" />
		</TagsGroup>
	
		<p>GDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurry</p>
		
		<div class="gdpsStats">
			<TagsGroup>
				<Tag icon={iconVisibility} label="950" />
				<Tag icon={iconStar} label="-50" />
				<Tag icon={iconFavorite} label="30" />
			</TagsGroup>
			
			<Tag icon={iconHistory} label="6 y. ago" />
		</div>
	</div>
</div>

<style>
	.gdps {
		background: var(--m3c-surface-container-highest);
		
		position: relative;
		max-width: 400px;
		
		cursor: pointer;
		user-select: none;
	}
	
	h1 {
		font-size: 1.2rem;
		color: var(--m3c-on-primary-container);
	}
	
	p {
		font-size: 1rem;
		max-height: 60px;
		overflow: hidden;
		color: var(--m3c-on-primary-container);
	}
	
	h2 {
		display: flex;
		align-items: center;
		gap: 5px;
		
		font-weight: 400;
		font-size: 18px;
		margin: 0px;
	}
	
	h3 {
		display: flex;
		align-items: center;
		gap: 5px;
		
		font-weight: 400;
		font-size: 14px;
		margin: 0px;
		
		color: var(--m3c-on-secondary-container);
		
		z-index: 2;
	}
	
	:global h2 > svg {
		max-height: 26px;
		max-width: 26px;
	}
	
	.bannerDiv {
		display: flex;
		
		max-width: 100%;
		aspect-ratio: 19/6;
		object-fit: cover;
		
		border-radius: var(--m3-shape-small);
		
		position: relative;
		z-index: 0;
	}
	
	.banner {
		max-width: 100%;
		width: 100%;
		height: 100%;
		object-fit: cover;
		
		border-radius: var(--m3-shape-small);
		border-top-left-radius: var(--m3-shape-large);
		border-top-right-radius: var(--m3-shape-large);
		
		z-index: 1;
	}
	
	.gdpsTitle {
		display: flex;
		align-items: flex-end;
		
		max-width: stretch;
		width: 100%;
		
		margin-left: -4.5px;
		margin-bottom: -5px;
		margin-top: -60px;
		
		padding-top: 10px;
		overflow-x: hidden;
	}
	
	.logo {
		position: relative;
		width: 100px;
		height: 100px;
		
		aspect-ratio: 1/1;
		object-fit: cover;
		
		border: 5px solid var(--m3c-surface-container-highest);
		background: var(--m3c-surface-container-highest);
		border-top-right-radius: var(--m3-shape-large);
	}
	
	.logo img {
		aspect-ratio: 1/1;
		object-fit: cover;
		
		width: 100%;
		border-radius: var(--m3-shape-medium);
		background: var(--m3c-on-secondary-container);
	}
	
	.logo:before,
	.logo:after {
		content: "";
		position: absolute;
		
		--border-padding: 4px;
		--border-size: calc(var(--m3-shape-small) + var(--border-padding));
		
		display: block;
		width: var(--border-size);
		height: var(--border-size);
		
		background: var(--m3c-surface-container-highest);
		corner-shape: scoop;
		
		border-top-right-radius: var(--m3-shape-small);
	}
	
	.logo:before {
		transform: translate(calc(var(--border-padding) * -1), calc(var(--border-padding) * -2 - 5px));
	}
	
	.logo:after {
		right: 0px;
		transform: translate(calc(var(--border-padding) * 3 + 0.5px), -58px);
	}
	
	.filler {
		opacity: 0;
		pointer-events: none;
		user-select: none;
	}
	
	.gdpsName {
		display: flex;
		flex-direction: column;
		padding: 0.2rem;
	}
	
	.gdpsDesc {
		display: flex;
		flex-direction: column;
		gap: 10px;
	}
	
	.gdpsStats {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		
		gap: 5px;
	}
	
	.gdpsStats > .gdpsStats {
		justify-content: flex-start;
	}
	
	.gdpsStats h2 {
		background: var(--m3c-secondary-container);
		color: var(--m3c-on-secondary-container);
		padding: .5rem;
		
		border-radius: var(--m3-shape-small);
		
		height: 40px;
	}
	
	.gdpsStats h2:nth-of-type(1) {
		border-top-left-radius: var(--m3-shape-large);
		border-bottom-left-radius: var(--m3-shape-large);
	}
	
	.gdpsStats h2:nth-last-of-type(1) {
		border-top-right-radius: var(--m3-shape-large);
		border-bottom-right-radius: var(--m3-shape-large);
	}
</style>