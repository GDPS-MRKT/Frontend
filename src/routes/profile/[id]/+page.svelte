<script>
	import { Icon, Button, LoadingIndicator } from "m3-svelte";
	import GDPSSmall from "../../../components/GDPSSmall.svelte";
	import TagsGroup from "../../../components/TagsGroup.svelte";
	import Tag from "../../../components/Tag.svelte";
	import Post from "../../../components/Post.svelte";
	
	import iconQuestionMark from "@ktibow/iconset-material-symbols/question-mark-rounded";
	import iconYouTube from "../../../lib/assets/logo_yt.svelte";
	import iconGitHub from "../../../lib/assets/logo_gh.svelte";
	import iconX from "../../../lib/assets/logo_x.svelte";
	import iconBluesky from "../../../lib/assets/logo_bs.svelte";
	import iconInstagram from "../../../lib/assets/logo_ig.svelte";
	import iconTikTok from "../../../lib/assets/logo_tt.svelte";
	import iconTelegram from "../../../lib/assets/logo_tg.svelte";
	import iconLink from "@ktibow/iconset-material-symbols/link-rounded";
	import iconSchedule from "@ktibow/iconset-material-symbols/schedule-rounded";
	import iconVisibility from "@ktibow/iconset-material-symbols/visibility-rounded";
	
	let { params } = $props();
	
	const userID = params.id;
	
	let profilePosts = $state([]);
	
	profilePosts.push(undefined);
	profilePosts.push(132);
	profilePosts.push(undefined);
	profilePosts.push(undefined);
	profilePosts.push(undefined);
	profilePosts.push(undefined);
	profilePosts.push(132);
</script>

<div class="profileWrapper">
	<div class="profileUser">
		<div class="profileInfo">
			<div class="profilePFPDiv">
				<img class="banner" src="https://images.gcs.skin/gcs/banner.png" alt="GDPS banner" />
				<img class="logo" src="https://images.gcs.skin/gcs/logo.png" alt="GDPS logo" />
			</div>
			
			<h2>Sa1ntSosetHui</h2>
			<p>GDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurry</p>
			
			<TagsGroup>
				<Tag icon={iconSchedule} title="Joined MRKT at" label="30.05.2026" />
				<Tag icon={iconVisibility} title="Last seen online" label="6 minutes ago" />
			</TagsGroup>
			
			<h3>Socials</h3>
			<div class="profileSocials">
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="YouTube">
					<svelte:component this={iconYouTube} /> YouTube
				</Button>
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="GitHub">
					<svelte:component this={iconGitHub} /> GitHub
				</Button>
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="GitHub">
					<svelte:component this={iconX} /> X
				</Button>
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="GitHub">
					<svelte:component this={iconBluesky} /> Bluesky
				</Button>
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="GitHub">
					<svelte:component this={iconInstagram} /> Instagram
				</Button>
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="GitHub">
					<svelte:component this={iconTikTok} /> TikTok
				</Button>
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="GitHub">
					<svelte:component this={iconTelegram} /> Telegram
				</Button>
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="Website">
					<Icon icon={iconLink} /> Website
				</Button>
			</div>
		</div>
		
		<div class="profileInfo">
			<h3>Owned</h3>
			<div class="profileGDPSs">
				<GDPSSmall />
				<GDPSSmall />
				<GDPSSmall />
			</div>
			
			<h3>Favorites</h3>
			<div class="profileGDPSs">
				<GDPSSmall />
				<GDPSSmall />
			</div>
		</div>
	</div>
	
	<div class="profilePosts">
		{#if !profilePosts.length}
			<div class="errorDiv">
				<h1><Icon icon={iconQuestionMark} /></h1>
				<h2>No posts.</h2>
			</div>
		{:else}
			{#each profilePosts as post}
				<Post gdpsID={post} />
			{/each}
		{/if}
	</div>
</div>

<style>
	.profileWrapper {
		display: flex;
		
		width: 80%;
		height: max-content;
		
		gap: 10px;
	}
	
	.profileInfo {
		display: flex;
		flex-direction: column;
		
		background: var(--m3c-surface-container-highest);
		border-radius: var(--m3-shape-large);
		
		width: 100%;
		height: max-content;
		padding: .75rem;
		
		gap: 5px;
	}
	
	.profileUser {
		display: flex;
		flex-direction: column;
		
		width: 80%;
		height: max-content;
		
		gap: 5px;
		
		position: sticky;
		top: -30px;
	}
	
	.profileInfo:nth-of-type(1) {
		border-top-left-radius: var(--m3-shape-extra-large);
		border-top-right-radius: var(--m3-shape-extra-large);
	}
	
	.profileInfo:nth-last-of-type(1) {
		border-bottom-left-radius: var(--m3-shape-extra-large);
		border-bottom-right-radius: var(--m3-shape-extra-large);
	}
	
	.profilePosts {
		display: flex;
		flex-direction: column;
		
		width: 100%;
		height: max-content;
		
		gap: 5px;
	}
	
	.profilePFPDiv {
		display: flex;
		flex-direction: column;
		align-items: center;
		
		max-width: 100%;
		aspect-ratio: 19/6;
		object-fit: cover;
		
		border-radius: var(--m3-shape-small);
		
		position: relative;
		z-index: 0;
		
		margin-bottom: 60px;
	}
	
	.banner {
		max-width: 100%;
		width: 100%;
		height: 100%;
		object-fit: cover;
		
		border-radius: var(--m3-shape-large);
		
		z-index: 1;
	}
	
	.logo {
		width: 130px;
		margin-top: -65px;
		
		border-radius: 100px;
		border: 5px solid var(--m3c-surface-container-highest);
		
		z-index: 2;
	}
	
	h2 {
		font-size: 30px;
		
		margin: 0px;
		text-align: center;
		
		color: var(--m3c-on-primary-container);
	}
	
	p {
		font-size: 1.1rem;
		overflow: hidden;
		
		margin-bottom: 5px;
		
		color: var(--m3c-on-primary-container);
	}
	
	h3 {
		margin: 0px;
		
		color: var(--m3c-on-primary-container);
	}
	
	.profileSocials	{
		display: flex;
		justify-content: flex-start;
		flex-wrap: wrap;
		
		gap: 5px;
		
		width: 100%;
	}
	
	.profileGDPSs {
		display: flex;
		flex-direction: column;
		
		gap: 5px;
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
		text-align: center;
		margin: 0px;
		font-size: 30px;
	}
</style>