<script>
	import { goto } from '$app/navigation';
	import { Icon, Button } from "m3-svelte";
	import Image from "./Image.svelte";
	import TagsGroup from "./TagsGroup.svelte";
	import Tag from "./Tag.svelte";
	import MenuGroup from "./MenuGroup.svelte";
	import Menu from "./Menu.svelte";
	import Comment from "./Comment.svelte";
	import Input from "./Input.svelte";
	import ConnectedElements from "./ConnectedElements.svelte";
	
	import iconFavorite from "@ktibow/iconset-material-symbols/favorite-rounded";
	import iconComment from "@ktibow/iconset-material-symbols/comment-rounded";
	import iconVisibility from "@ktibow/iconset-material-symbols/visibility-rounded";
	import iconMoreHoriz from "@ktibow/iconset-material-symbols/more-horiz";
	import iconLink from "@ktibow/iconset-material-symbols/link-rounded";
	import iconFlag from "@ktibow/iconset-material-symbols/flag-rounded";
	import iconReply from "@ktibow/iconset-material-symbols/reply-rounded";
	
	let { gdpsID } = $props();
	
	let showCommentButton = $state(false);
</script>

<div class="postElements">
	<ConnectedElements>
		<div class="post containsMenu connectedElement">
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
						<Tag label="2 weeks ago" />
						{#if gdpsID != undefined}
							<Tag label="For GreenCatsServer" onClick={() => goto("/gdps/Sa1ntSosetHui")} />
						{/if}
					</TagsGroup>
				</div>
				
				<MenuGroup icon={iconMoreHoriz}>
					<Menu onClick={() => {}} icon={iconLink} label="Copy link" />
					<Menu onClick={() => {}} icon={iconFlag} label="Report" />
				</MenuGroup>
			</div>
			
			<p>GDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurry</p>
			
			<div class="postButtons">
				<div class="postButtonsGroup">
					<TagsGroup>
						<Tag icon={iconFavorite} label="10" color={gdpsID != undefined ? "primary" : null} onClick={() => console.log(123)} />
						<Tag icon={iconComment} label="2" onClick={() => console.log(123)} />
					</TagsGroup>
					
					<TagsGroup>
						<Tag color="text" icon={iconReply} label="Reply" onClick={() => showCommentButton = !showCommentButton} />
					</TagsGroup>
				</div>
				
				<TagsGroup>
					<Tag icon={iconVisibility} label="42" />
				</TagsGroup>
			</div>
		</div>
		
		{#if gdpsID != undefined}
			<Comment />
		{/if}
		
		<div class={["inputField connectedElement", (!showCommentButton ? " hide" : "")].join(" ")}>
			<Input label="Write a comment..." />
		</div>
	</ConnectedElements>
</div>

<style>
	.post {
		display: flex;
		flex-direction: column;
		
		background: var(--m3c-surface-container-highest);
		
		width: 100%;
		padding: 1rem;
		
		gap: 10px;
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
		overflow: hidden;
		
		aspect-ratio: 1/1;
	}
	
	/*
		Сквозь border у самого элемента видно элементы сзади
	*/
	.postGDPSLogo::after {
		content: '';
		
		position: absolute;
		top: 0px;
		
		width: 100%;
		height: 100%;
		
		border: 3px solid var(--m3c-surface-container-highest);
		border-radius: 10px;
		
		z-index: 2;
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
	
	.inputField {
		display: flex;
		flex-direction: column;
		
		background: var(--m3c-surface-container-highest);
		
		width: 100%;
		max-height: max-content;
		padding: 0px .75rem;
		
		gap: 10px;
		
		transition: var(--m3-easing-slow);
		interpolate-size: allow-keywords;
		overflow: hidden;
	}
	
	:global .inputField > div {
		margin: .75rem 0px;
	}
	
	.inputField.hide {
		max-height: 0px;
		
		visibility: hidden;
		
		margin-bottom: -3px;
	}
	
	.postElements {
		display: flex;
		flex-direction: column;
		
		gap: 3px;
		
		width: 0px;
		min-width: 100%;
	}
	
	.postButtonsGroup {
		display: flex;
		
		gap: 5px;
	}
</style>