<script>
	import { onMount } from 'svelte';
	import { Icon, Button, Dialog } from "m3-svelte";
	import Image from "../../../../components/Image.svelte";
	import Header from "../../../../components/Header.svelte";
	import Setting from "../../../../components/Setting.svelte";
	import TagsGroup from "../../../../components/TagsGroup.svelte";
	import Tag from "../../../../components/Tag.svelte";
	import DialogInfo from "../../../../components/DialogInfo.svelte";
	
	import iconQuestionMark from "@ktibow/iconset-material-symbols/question-mark-rounded";
	import iconYouTube from "../../../../lib/assets/logo_yt.svelte";
	import iconGitHub from "../../../../lib/assets/logo_gh.svelte";
	import iconX from "../../../../lib/assets/logo_x.svelte";
	import iconBluesky from "../../../../lib/assets/logo_bs.svelte";
	import iconInstagram from "../../../../lib/assets/logo_ig.svelte";
	import iconTikTok from "../../../../lib/assets/logo_tt.svelte";
	import iconDiscord from "../../../../lib/assets/logo_ds.svelte";
	import iconTelegram from "../../../../lib/assets/logo_tg.svelte";
	import iconLink from "@ktibow/iconset-material-symbols/link-rounded";
	import iconEdit from "@ktibow/iconset-material-symbols/edit-rounded";
	import iconPerson from "@ktibow/iconset-material-symbols/person-rounded";
	import iconComment from "@ktibow/iconset-material-symbols/comment-rounded";
	import iconEmail from "@ktibow/iconset-material-symbols/alternate-email-rounded";
	import iconInfo from "@ktibow/iconset-material-symbols/info-i-rounded";
	
	let { params } = $props();
	
	const userID = params.id;
	
	let socialsArray = $state([
		{title: "YouTube", value: "@Sa1ntSosetHui", icon: iconYouTube},
		{title: "GitHub", value: "MegaSa1nt", icon: iconGitHub},
		{title: "X", value: "", icon: iconX},
		{title: "Bluesky", value: "", icon: iconBluesky},
		{title: "Instagram", value: "", icon: iconInstagram},
		{title: "TikTok", value: "megasa1nt", icon: iconTikTok},
		{title: "Discord", value: "sa1ntsosethui", icon: iconDiscord},
		{title: "Telegram", value: "MegaSa1nt", icon: iconTelegram},
		{title: "Website", value: "https://socials.gcs.skin", icon: iconLink},
	]);
	
	let dialogEmail = $state(false);
	let dialogDiscordID = $state(false);
	
	let profileStick = $state("bottom");
	let elementStick = () => {
		profileStick = profileStickElement.scrollHeight > (window.innerHeight - 60) ? "bottom" : "top";
	}
	onMount(() => {
		let profileStickElement = document.getElementById("profileStickElement");
		elementStick();
	});
</script>

<Header title="Sa1ntSosetHui's settings" />

<svelte:window on:resize={elementStick} />

<div class="profileWrapper">
	<div class="profileUser" id="profileStickElement" stick={profileStick}>
		<div class="profileInfo">
			<div class="profilePFPDiv">
				<span class="profilePFPBanner">
					<div class="profileEditButton">
						<Icon icon={iconEdit} /> Edit
					</div>
					<Image src="https://images.gcs.skin/gcs/banner.png" title="GDPS banner" />
				</span>
				
				<span class="profilePFPLogo">
					<div class="profileEditButton">
						<Icon icon={iconEdit} />
					</div>
					<Image src="https://images.gcs.skin/gcs/logo.png" title="GDPS logo" />
				</span>
			</div>
			
			<h2>Sa1ntSosetHui</h2>
			<p>GDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurryGDPS description. Very good GDPS. Good GDPS. Good boy. femboyfemboyfurry</p>
			
			<h3>Socials</h3>
			<TagsGroup>
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="YouTube">
					<svelte:component this={iconYouTube} /> YouTube
				</Button>
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="GitHub">
					<svelte:component this={iconGitHub} /> GitHub
				</Button>
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="X">
					<svelte:component this={iconX} /> X
				</Button>
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="Bluesky">
					<svelte:component this={iconBluesky} /> Bluesky
				</Button>
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="Instagram">
					<svelte:component this={iconInstagram} /> Instagram
				</Button>
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="TikTok">
					<svelte:component this={iconTikTok} /> TikTok
				</Button>
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="Discord">
					<svelte:component this={iconDiscord} /> Discord
				</Button>
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="Telegram">
					<svelte:component this={iconTelegram} /> Telegram
				</Button>
				<Button target="_blank" rel="noopener" href="https://gcs.skin" title="Website">
					<Icon icon={iconLink} /> Website
				</Button>
			</TagsGroup>
		</div>
	</div>
	
	<div class="profileSettings">
		<div class="profileInfo">
			<Setting icon={iconPerson} title="Username" value="Sa1ntSosetHui">
				<Button iconType="full">
					<Icon icon={iconEdit} />
				</Button>
			</Setting>
			
			<Setting icon={iconComment} title="Description" value="You can use Markdown in descriptions">
				<Button iconType="full">
					<Icon icon={iconEdit} />
				</Button>
			</Setting>
			
			<Setting icon={iconEmail} title="Email address" value="m**********8@g***l.com">
				<Button variant="tonal" iconType="full" onclick={() => dialogEmail = !dialogEmail}>
					<Icon icon={iconInfo} />
					<DialogInfo title="Email address" description={["This is the email of the Discord account you use to login to MRKT.", "It will automatically sync on every login."]} button="OK" open={dialogEmail} />
				</Button>
			</Setting>
			
			<Setting icon={iconDiscord} title="Discord ID" value="297295491417505793">
				<Button variant="tonal" iconType="full" onclick={() => dialogDiscordID = !dialogDiscordID}>
					<Icon icon={iconInfo} />
					<DialogInfo title="Discord ID" description="This is the ID of the Discord account you use to login to MRKT." button="OK" open={dialogDiscordID} />
				</Button>
			</Setting>
		</div>
		
		<div class="profileInfo">
			{#each socialsArray as social}
				<Setting icon={social.icon} title={social.title} value={social.value.length ? social.value : "Unset"}>
					<Button iconType="full">
						<Icon icon={iconEdit} />
					</Button>
				</Setting>
			{/each}
		</div>
	</div>
</div>

<style>
	.profileWrapper {
		display: flex;
		
		width: 65rem;
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
	
	.profileSettings .profileInfo {
		padding: 0px;
		background: transparent;
	}
	
	.profileUser {
		display: flex;
		flex-direction: column;
		align-self: flex-end;
		
		width: 80%;
		height: max-content;
		
		gap: 5px;
		
		position: sticky;
		bottom: -30px;
	}
	
	.profileUser[stick="top"] {
		bottom: initial;
		top: -30px;
		
		align-self: initial;
	}
	
	.profileInfo:nth-of-type(1) {
		border-top-left-radius: var(--m3-shape-extra-large);
		border-top-right-radius: var(--m3-shape-extra-large);
	}
	
	.profileInfo:nth-last-of-type(1) {
		border-bottom-left-radius: var(--m3-shape-extra-large);
		border-bottom-right-radius: var(--m3-shape-extra-large);
	}
	
	.profileSettings {
		display: flex;
		flex-direction: column;
		
		width: 100%;
		height: max-content;
		
		gap: 10px;
	}
	
	.profilePFPDiv {
		display: flex;
		flex-direction: column;
		align-items: center;
		
		max-width: 100%;
		object-fit: cover;
		
		border-radius: var(--m3-shape-small);
		
		position: relative;
		z-index: 0;
		
		user-select: none;
	}
	
	.profilePFPBanner {
		position: relative;
		
		max-width: 100%;
		width: 100%;
		height: 100%;
		object-fit: cover;
		aspect-ratio: 19/6;
		
		border-radius: var(--m3-shape-large);
		overflow: hidden;
		
		z-index: 1;
	}
	
	.profileEditButton {
		position: absolute;
		
		display: flex;
		justify-content: center;
		align-items: center;
		
		font-size: 1.3rem;
		font-weight: 500;
		gap: 5px;
		
		width: 100%;
		height: 100%;
		
		background: color-mix(in srgb, var(--m3c-surface-container-highest) 60%, transparent);
		
		opacity: 0;
		cursor: pointer;
		transition: var(--m3-easing-fast);
	}
	
	.profilePFPBanner .profileEditButton {
		padding: .75rem;
		
		justify-content: flex-start;
		align-items: flex-start;
	}
	
	.profileEditButton:hover {
		opacity: 1;
	}
	
	.profilePFPLogo {
		position: relative;
		
		max-width: 130px;
		max-height: 130px;
		margin-top: -65px;
		
		border-radius: 100px;
		border: 5px solid var(--m3c-surface-container-highest);
		overflow: hidden;
		
		z-index: 2;
	}
	
	h2 {
		font-size: 1.6rem;
		
		margin: 0px;
		text-align: center;
		
		color: var(--m3c-on-primary-container);
	}
	
	p {
		font-size: 1rem;
		overflow: hidden;
		
		margin-bottom: 5px;
		
		color: var(--m3c-on-primary-container);
	}
	
	h3 {
		margin: 0px;
		
		color: var(--m3c-on-primary-container);
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