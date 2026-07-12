<script>
	import { goto } from '$app/navigation';
	import { Icon, Button } from "m3-svelte";
	import TagsGroup from "./TagsGroup.svelte";
	import Tag from "./Tag.svelte";
	
	import iconFavorite from "@ktibow/iconset-material-symbols/favorite-rounded";
	import iconComment from "@ktibow/iconset-material-symbols/comment-rounded";
	import iconVisibility from "@ktibow/iconset-material-symbols/visibility-rounded";
	
	let { gdpsID } = $props();
</script>

<div class="post">
	<div class="postTitle">
		<span class="logo">
			<img src="https://images.gcs.skin/gcs/logo.png" alt="GDPS logo" />
			
			{#if gdpsID != undefined}
				<img src="https://images.gcs.skin/gcs/logo.png" alt="GDPS logo" />
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
	</div>
	
	<p>GDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurry</p>
	
	<div class="postButtons">
		<TagsGroup>
			{#if gdpsID != undefined}
				<Tag icon={iconFavorite} label="10" color="primary" onClick={() => console.log(123)} />
			{:else}
				<Tag icon={iconFavorite} label="10" />
			{/if}
			<Tag icon={iconComment} label="2" />
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
		font-size: 1.1rem;
		overflow: hidden;
		
		color: var(--m3c-on-primary-container);
	}
	
	.logo {
		height: 50px;
		
		position: relative;
	}
	
	.logo img {
		height: 50px;
		border-radius: 100px;
	}
	
	.logo img:nth-of-type(2) {
		height: 26px;
		border-radius: 100px;
		
		position: absolute;
		
		bottom: -3px;
		right: -3px;
		border: 3px solid var(--m3c-surface-container-highest);
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