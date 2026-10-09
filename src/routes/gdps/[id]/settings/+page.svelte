<script>
	import { onMount } from 'svelte';
	import { goto } from '$app/navigation';
	import { Icon, Button, Dialog } from "m3-svelte";
	import Image from "../../../../components/Image.svelte";
	import Header from "../../../../components/Header.svelte";
	import Setting from "../../../../components/Setting.svelte";
	import TagsGroup from "../../../../components/TagsGroup.svelte";
	import Tag from "../../../../components/Tag.svelte";
	import ConnectedElements from "../../../../components/ConnectedElements.svelte";
	
	import iconVisibility from "@ktibow/iconset-material-symbols/visibility-rounded";
	import iconThumbUp from "@ktibow/iconset-material-symbols/thumb-up-rounded";
	import iconThumbDown from "@ktibow/iconset-material-symbols/thumb-down-rounded";
	import iconFavorite from "@ktibow/iconset-material-symbols/favorite-rounded";
	import iconComment from "@ktibow/iconset-material-symbols/comment-rounded";
	import iconHistory from "@ktibow/iconset-material-symbols/history-rounded";
	import iconStar from "@ktibow/iconset-material-symbols/star-rounded";
	import iconDesktopWindows from "@ktibow/iconset-material-symbols/desktop-windows-outline-rounded";
	import iconAndroid from "@ktibow/iconset-material-symbols/android";
	import iconDesktopMac from "@ktibow/iconset-material-symbols/desktop-mac-outline-rounded";
	import iconIos from "@ktibow/iconset-material-symbols/ios";
	import iconDiscord from "../../../../lib/assets/logo_ds.svelte";
	import iconTelegram from "../../../../lib/assets/logo_tg.svelte";
	import iconMoreHoriz from "@ktibow/iconset-material-symbols/more-horiz";
	import iconFlag from "@ktibow/iconset-material-symbols/flag-rounded";
	import iconYouTube from "../../../../lib/assets/logo_yt.svelte";
	import iconLink from "@ktibow/iconset-material-symbols/link-rounded";
	import iconEdit from "@ktibow/iconset-material-symbols/edit-rounded";
	import iconEditSquare from "@ktibow/iconset-material-symbols/edit-square-rounded";
	import iconPerson from "@ktibow/iconset-material-symbols/person-rounded";
	import iconEmail from "@ktibow/iconset-material-symbols/alternate-email-rounded";
	import iconInfo from "@ktibow/iconset-material-symbols/info-i-rounded";
	
	let { params } = $props();
	
	const userID = params.id;
	
	let downloadsArray = $state([
		{id: "pc", title: "PC", description: ["Download link for Windows."], value: "https://gcs.skin/pc", icon: iconDesktopWindows},
		{id: "android", title: "Android", description: ["Download link for Android."], value: "https://gcs.skin/android", icon: iconAndroid},
		{id: "macos", title: "macOS", description: ["Download link for macOS."], value: "https://gcs.skin/macos", icon: iconDesktopMac},
		{id: "ios", title: "iOS", description: ["Download link for iOS."], value: "https://gcs.skin/ios", icon: iconIos},
	]);
	let socialsArray = $state([
		{id: "discord", title: "Discord", description: ["Link to GDPS Discord server."], value: "sa1ntsosethui", icon: iconDiscord},
		{id: "telegram", title: "Telegram", description: ["Link to GDPS Telegram channel."], value: "MegaSa1nt", icon: iconTelegram},
		{id: "website", title: "Website", description: ["Link to GDPS website, for example, dashboard or main page."], value: "https://socials.gcs.skin", icon: iconLink},
	]);

	let gdpsInfoStick = $state("bottom");
	let elementStick = () => {
		gdpsInfoStick = gdpsInfoStickElement.scrollHeight > (window.innerHeight - 60) ? "bottom" : "top";
	}
	onMount(() => {
		let gdpsInfoStickElement = document.getElementById("gdpsInfoStickElement");
		elementStick();
	});
	
	const gdpsDescription = `## ХЕШТЕГИ GreenCatsServer \\#ФурриВологды #FurryOfVologda #ФурриТожеЛюди #LetFurriesLive #Mrow #PlayGreenCatsServer #ImFurryGang #OMORI #GREEN #11111111 #AIBot #МальчикЕщёНеВырос #FurrySa1nt #MaidSa1nt #FurryMaid #ЯЛюблюПШП #PHPIsMyLife #HatKidIsMyFav #Maksidem #GCS #GD2.2 #Hashtag #7-8 #КакойЖеЯЕбучий #Эщкере #:3 #FemboyGDPS #FurryGDPS #42 #goglepixel #комачячи #НовостиКаждыйЧас #коленвал #привет #не #НовыйСленг #ПиксельБаттл #ВоСлавуГКС #ОВеликийGreenCatsServer #Топ1!!!!!! #Boykisser #Niko #OneShot #M336 #Cold #ЪЭ #AntiAmogusPolicy #ЁбаныеАмогусы #ФУРЭ #ФУРРИ #ФУРРИ #FURRY #F*RRY #FURRY #FURE #ФУРРЭ #МЯУМЯУУМЯУМЯУМУМЯМУМЯМ #FURRYPLACE #FURRYISGETTINGDISCRIMINATEDONGDPSHUB!!!!!!!!!!!!!!!!! #FURRY #FURRYFURRYFURFYURYFUYFURYFURYUYFUYRFURYFURYFRUYFRU #FURI #FURRI #FURRE #кэбокс #кэбокс #кэбокс #кэбокс #кэбокс #мармеладка #уточка #ФУРРИУТОЧКАРЕАЛЬНО #ФурриФембоиТут #ihatejuchil #UnmuteGrechka #GRECHKA #Outcore #PLEASELUMI #SFWServer #NoP\\*rnAllowed!!! #NoJ\\*b #NoEmpl\\*yment #NoRel\\*tionships #NoSt\\*dying #NoA\\*\\*le #PIXELGANG #GOGLEPIXELGANG #BoykisserXGirlkisser #EMOTIONS #ФурэМилашкэ #АНТИХАЙП #ANTIHYPE #ХАНЗАМАЙ #OBLADAUN #ГИМН #ГимнGreenCatsServerСлушатьВсемИКаждомуИЕщёЛайкПоставитьИНаписатьПоложительныйКомментарийХорошийСлушатьВсемGreenCatsServerаКотикГорничнойБытьНеПротивХорошийГимн`;
</script>

<Header title="Sa1ntSosetHui's settings" />

<svelte:window on:resize={elementStick} />

<div class="gdpsWrapper">
	<div class="gdpsBannerDiv">
		<div class="gdpsEditButton">
			<Icon icon={iconEdit} /> Edit
		</div>
		<Image src="https://images.gcs.skin/gcs/banner.png" title="GDPS banner" />
	</div>
	
	<div class="gdpsPage">
		<div class="gdpsInfo short" id="gdpsInfoStickElement" stick={gdpsInfoStick}>
			<ConnectedElements>
				<div class="gdpsCard connectedElement">
					<div class="gdpsTitle">
						<span class="logo">
							<div class="gdpsEditButton">
								<Icon icon={iconEdit} />
							</div>
							<Image src="https://images.gcs.skin/gcs/logo.png" alt="https://images.gcs.skin/mrkt/logo.png" title="GDPS logo" />
						</span>
						
						<div class="gdpsName">
							<h1>GreenCatsServer</h1>
							<h3 on:click={() => goto("/profile/Sa1ntSosetHui")}>Sa1ntSosetHui</h3>
							
							<TagsGroup size="small">
								<Tag icon={iconStar} color="gold" label="Recommended" />
								<Tag label="2.2" />
								<Tag label="GCS" />
								<Tag label="Femboys" />
								<Tag label="Furi" />
							</TagsGroup>
						</div>
					</div>
				</div>
				
				<div class="gdpsCard connectedElement">
					<h2>Download GDPS</h2>
					<TagsGroup>
						<Button target="_blank" rel="noopener" href="https://gcs.skin" title="PC">
							<Icon icon={iconDesktopWindows} /> PC
						</Button>
						<Button target="_blank" rel="noopener" href="https://gcs.skin" title="Android">
							<Icon icon={iconAndroid} /> Android
						</Button>
						<Button target="_blank" rel="noopener" href="https://gcs.skin" title="macOS">
							<Icon icon={iconDesktopMac} /> macOS
						</Button>
						<Button target="_blank" rel="noopener" href="https://gcs.skin" title="iOS">
							<Icon icon={iconIos} /> iOS
						</Button>
					</TagsGroup>
					
					<h2>Socials</h2>
					<TagsGroup>
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
				
				<div class="gdpsCard connectedElement">
					<h2>Trailer</h2>
					<iframe class="gdpsTrailer" src="https://www.youtube.com/embed/w8IIW2Bu_1A" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
				</div>
			</ConnectedElements>
		</div>
		
		<form class="gdpsSettings" name="gdps-settings" method="post" action=".">
			<div class="gdpsInfo">
				<h4>Information</h4>
				
				<ConnectedElements size="large-increased">
					<Setting
						id="name"
						icon={iconEditSquare}
						title="Name"
						value="GreenCatsServer"
						type="input"
						description={["Name for your GDPS."]}
					/>
					
					<Setting
						id="description"
						icon={iconComment}
						title="Description"
						value={gdpsDescription}
						type="info"
						description={["Description of your GDPS.", "You can use Markdown in descriptions."]}
					/>
					
					<Setting
						id="trailer"
						icon={iconYouTube}
						title="Trailer"
						value="w8IIW2Bu_1A"
						type="input"
						description={["YouTube video trailer of your GDPS.", "For example, if your YouTube video link is https://www.youtube.com/watch?v=w8IIW2Bu_1A, then put w8IIW2Bu_1A."]}
					/>
					
					<Setting
						icon={iconInfo}
						title="Status"
						value="Pending"
						type="info"
						description={["This GDPS is currently unlisted.", "It will become public once it passes the verification process."]}
					/>
				</ConnectedElements>
			</div>
			
			<div class="gdpsInfo">
				<h4>Download links</h4>
				
				<ConnectedElements size="large-increased">
					{#each downloadsArray as download}
						<Setting
							id={download.id}
							icon={download.icon}
							title={download.title}
							value={download.value}
							type="input"
							description={download.description}
						/>
					{/each}
				</ConnectedElements>
			</div>
			
			<div class="gdpsInfo">
				<h4>Socials</h4>
			
				<ConnectedElements size="large-increased">
					{#each socialsArray as social}
						<Setting
							id={social.id}
							icon={social.icon}
							title={social.title}
							value={social.value}
							type="input"
							description={social.description}
						/>
					{/each}
				</ConnectedElements>
			</div>
		</form>
	</div>
</div>

<style>
	.gdpsWrapper {
		display: flex;
		flex-direction: column;
		
		width: 75rem;
		height: max-content;
		
		gap: 10px;
	}
	
	.gdpsBannerDiv {
		display: flex;
		flex-direction: column;
		align-items: center;
		
		max-width: 100%;
		aspect-ratio: 21/4;
		object-fit: cover;
		
		border-radius: var(--m3-shape-extra-large);
		overflow: hidden;
		
		position: relative;
		z-index: 0;
	}
	
	.gdpsPage {
		display: flex;
		gap: 10px;
		
		width: 100%;
		position: relative;
	}
	
	.gdpsInfo {
		display: flex;
		flex-direction: column;
		
		gap: 5px;
		
		width: 100%;
		height: 100%;
	}
	
	.gdpsInfo.short {
		width: 70%;
		
		position: sticky;
		bottom: -30px;
		align-self: flex-end;
	}
	
	.gdpsInfo.short[stick="top"] {
		bottom: initial;
		top: -30px;
		
		align-self: initial;
	}
	
	.gdpsSettings .gdpsInfo {
		gap: 3px;
	}
	
	.gdpsCard {
		display: flex;
		flex-direction: column;
		
		background: var(--m3c-surface-container-highest);
		
		width: 100%;
		height: max-content;
		padding: .75rem;
		overflow-wrap: anywhere;
		
		gap: 10px;
	}
	
	.gdpsCard.gdpsDescription {
		color: var(--m3c-on-secondary-container);
		
		gap: 5px;
	}
	
	.gdpsTitle {
		display: flex;
		align-items: center;
		
		gap: 10px;
	}
	
	.gdpsTitle h1 {
		font-size: 1.5rem;
		color: var(--m3c-on-primary-container);
	}
	
	.gdpsTitle h3 {
		font-weight: 400;
		font-size: 1.2rem;
		
		margin: 0px;
		margin-top: -5px;
		
		color: var(--m3c-on-secondary-container);
		transition: color var(--m3-easing-fast);
		
		cursor: pointer;
	}
	
	.gdpsTitle h3:hover {
		color: var(--m3c-on-primary-container);
	}
	
	.gdpsName {
		display: flex;
		flex-direction: column;
		
		gap: 5px;
	}
	
	.gdpsName h1 {
		font-weight: 700;
	}
	
	.gdpsTitle .logo {
		max-height: 90px;
		max-width: 90px;
		width: 100%;
		height: 100%;
		
		border-radius: var(--m3-shape-large);
		overflow: hidden;
		
		aspect-ratio: 1/1;
		position: relative;
	}
	
	.gdpsStats {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		flex-wrap: wrap;
		
		gap: 5px;
	}
	
	h2 {
		color: var(--m3c-on-primary-container);
		font-size: 1.4rem;
		font-weight: 800;
		margin: 0px;
	}
	
	h4 {
		color: var(--m3c-on-secondary-container);
		font-size: 1rem;
		font-weight: 600;
		
		margin: 0px;
		margin-left: .75rem;
	}
	
	.gdpsTrailer {
		border-radius: var(--m3-shape-large);
		
		width: 100%;
		height: 100%;
		
		aspect-ratio: 16/9;
	}
	
	.gdpsSettings {
		display: flex;
		flex-direction: column;
		
		width: 100%;
		height: max-content;
		
		gap: 10px;
	}
	
	.gdpsEditButton {
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
		
		z-index: 2;
	}
	
	.gdpsEditButton:hover {
		opacity: 1;
	}
</style>