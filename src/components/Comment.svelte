<script>
	import { goto } from '$app/navigation';
	import { Icon } from "m3-svelte";
	import Image from "./Image.svelte";
	import TagsGroup from "./TagsGroup.svelte";
	import Tag from "./Tag.svelte";
	
	import iconFavorite from "@ktibow/iconset-material-symbols/favorite-rounded";
	
	//let { icon, label, color, title, onClick } = $props();
</script>

<div class="postComment connectedElement">
	<span class="postPFP">
		<Image src="https://images.gcs.skin/gcs/logo.png" title="GDPS logo" />
	</span>
	
	<h1 on:click={() => goto("/profile/Sa1ntSosetHui")}>Sa1ntSosetHui</h1>
	<TagsGroup size="small" wrap="nowrap">
		<p>GDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurry</p>
		<Tag label={30} icon={iconFavorite} onClick={() => {}} />
	</TagsGroup>
</div>

<style>
	.postComment {
		display: flex;
		align-items: center;
		flex-direction: row;
		
		background: var(--m3c-surface-container-highest);
		
		width: 100%;
		padding: .5rem .75rem;
		
		gap: 5px;
		
		position: relative;
	}
	
	.postPFP {
		display: block;
		
		max-height: 25px;
		max-width: 25px;
		width: 100%;
		height: 100%;
		
		border-radius: 100px;
		overflow: hidden;
		
		aspect-ratio: 1/1;
	}
	
	h1 {
		font-size: 1.1rem;
		color: var(--m3c-on-primary-container);
		
		cursor: pointer;
	}
	
	p {
		font-size: 1rem;
		overflow: hidden;
		
		color: var(--m3c-on-primary-container);
		
		white-space: nowrap;
		text-overflow: ellipsis;
	}
</style>