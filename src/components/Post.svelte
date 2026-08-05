<script>
	import { goto } from '$app/navigation';
	import { Icon, Button } from "m3-svelte";
	import Image from "./Image.svelte";
	import TagsGroup from "./TagsGroup.svelte";
	import Tag from "./Tag.svelte";
	import MenuGroup from "./MenuGroup.svelte";
	import MenuItems from "./MenuItems.svelte";
	import Menu from "./Menu.svelte";
	
	import iconFavorite from "@ktibow/iconset-material-symbols/favorite-rounded";
	import iconComment from "@ktibow/iconset-material-symbols/comment-rounded";
	import iconVisibility from "@ktibow/iconset-material-symbols/visibility-rounded";
	import iconMoreHoriz from "@ktibow/iconset-material-symbols/more-horiz";
	import iconLink from "@ktibow/iconset-material-symbols/link-rounded";
	import iconFlag from "@ktibow/iconset-material-symbols/flag-rounded";
	
	let { gdpsID } = $props();
</script>

<div class="post containsMenu">
	<div class="postTitle">
		<span class="postLogos">
			<span class="postPFP">
				<Image src="https://images.gcs.skin/gcs/logo.png" title="GDPS logo" />
			</span>
			
			{#if gdpsID != undefined}
				<span class="postGDPSLogo">
					<Image src="https://images.gcs.skin/gcs/logo.png" title="GDPS logo" />
				</span>
			{/if}
		</span>
		
		<div class="postName">
			<h1 on:click={() => goto("/profile/Sa1ntSosetHui")}>Sa1ntSosetHui</h1>
			
			<TagsGroup size="small">
				{#if gdpsID != undefined}
					<Tag label="For GreenCatsServer" onClick={() => goto("/gdps/Sa1ntSosetHui")} />
				{/if}
				<Tag label="2 weeks ago" />
			</TagsGroup>
		</div>
		
		<MenuGroup icon={iconMoreHoriz}>
			<MenuItems>
				<Menu onClick={() => {}} icon={iconLink} label="Copy link" />
				<Menu onClick={() => {}} icon={iconFlag} label="Report" />
			</MenuItems>
		</MenuGroup>
	</div>
	
	<p>GDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurry</p>
	
	<div class="postButtons">
		<TagsGroup>
			<Tag icon={iconFavorite} label="10" color={gdpsID != undefined ? "primary" : null} onClick={() => console.log(123)} />
			<Tag icon={iconComment} label="2" onClick={() => console.log(123)} />
		</TagsGroup>
		
		<TagsGroup>
			<Tag icon={iconVisibility} label="42" />
		</TagsGroup>
	</div>
</div>

<style>
	.post {
		display: flex;
		flex-direction: column;
		
		background: var(--m3c-surface-container-highest);
		
		width: 100%;
		padding: 1rem;
		border-radius: var(--m3-shape-large);
		
		gap: 10px;
	}
	
	.post:nth-of-type(1) {
		border-top-left-radius: var(--m3-shape-extra-large);
		border-top-right-radius: var(--m3-shape-extra-large);
	}
	
	.post:nth-last-of-type(1) {
		border-bottom-left-radius: var(--m3-shape-extra-large);
		border-bottom-right-radius: var(--m3-shape-extra-large);
	}
	
	h1 {
		font-size: 1.4rem;
		color: var(--m3c-on-primary-container);
		
		cursor: pointer;
	}
	
	h3 {
		font-weight: 400;
		font-size: 16px;
		margin: 0px;
		
		color: var(--m3c-on-secondary-container);
	}
	
	p {
		font-size: 1rem;
		overflow: hidden;
		
		color: var(--m3c-on-primary-container);
	}
	
	.postLogos {
		max-height: 50px;
		max-width: 50px;
		width: 100%;
		
		position: relative;
	}
	
	.postPFP {
		display: block;
		
		max-height: 50px;
		max-width: 50px;
		width: 100%;
		height: 100%;
		
		border-radius: 100px;
		overflow: hidden;
		
		aspect-ratio: 1/1;
	}
	
	.postGDPSLogo {
		max-height: 26px;
		max-width: 26px;
		width: 100%;
		height: 100%;
		border-radius: 10px;
		
		position: absolute;
		
		bottom: -3px;
		right: -3px;
		border: 3px solid var(--m3c-surface-container-highest);
		overflow: hidden;
		
		aspect-ratio: 1/1;
	}
	
	.postTitle {
		display: flex;
		align-items: center;
		
		gap: 7px;
	}
	
	.postName {
		display: flex;
		flex-direction: column;
	}
	
	.postButtons {
		display: flex;
		justify-content: space-between;
		
		width: 100%;
	}
</style>