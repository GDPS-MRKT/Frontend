<script>
	import { onMount } from 'svelte';
	import { goto } from '$app/navigation';
	import { Icon, Button, LoadingIndicator } from "m3-svelte";
	import Image from "../../../components/Image.svelte";
	import Markdown from "../../../components/Markdown.svelte";
	import Header from "../../../components/Header.svelte";
	import TagsGroup from "../../../components/TagsGroup.svelte";
	import Tag from "../../../components/Tag.svelte";
	import Post from "../../../components/Post.svelte";
	import Input from "../../../components/Input.svelte";
	import MenuGroup from "../../../components/MenuGroup.svelte";
	import MenuItems from "../../../components/MenuItems.svelte";
	import Menu from "../../../components/Menu.svelte";
	
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
	import iconDiscord from "../../../lib/assets/logo_ds.svelte";
	import iconTelegram from "../../../lib/assets/logo_tg.svelte";
	import iconLink from "@ktibow/iconset-material-symbols/link-rounded";
	import iconMoreHoriz from "@ktibow/iconset-material-symbols/more-horiz";
	import iconFlag from "@ktibow/iconset-material-symbols/flag-rounded";
	import iconEdit from "@ktibow/iconset-material-symbols/edit-rounded";
	
	let { params } = $props();
	
	const gdpsID = params.id;
	
	const gdpsDescription = `## ХЕШТЕГИ GreenCatsServer

\\#ФурриВологды #FurryOfVologda #ФурриТожеЛюди #LetFurriesLive #Mrow #PlayGreenCatsServer #ImFurryGang #OMORI #GREEN #11111111 #AIBot #МальчикЕщёНеВырос #FurrySa1nt #MaidSa1nt #FurryMaid #ЯЛюблюПШП #PHPIsMyLife #HatKidIsMyFav #Maksidem #GCS #GD2.2 #Hashtag #7-8 #КакойЖеЯЕбучий #Эщкере #:3 #FemboyGDPS #FurryGDPS #42 #goglepixel #комачячи #НовостиКаждыйЧас #коленвал #привет #не #НовыйСленг #ПиксельБаттл #ВоСлавуГКС #ОВеликийGreenCatsServer #Топ1!!!!!! #Boykisser #Niko #OneShot #M336 #Cold #ЪЭ #AntiAmogusPolicy #ЁбаныеАмогусы #ФУРЭ #ФУРРИ #ФУРРИ #FURRY #F*RRY #FURRY #FURE #ФУРРЭ #МЯУМЯУУМЯУМЯУМУМЯМУМЯМ #FURRYPLACE #FURRYISGETTINGDISCRIMINATEDONGDPSHUB!!!!!!!!!!!!!!!!! #FURRY #FURRYFURRYFURFYURYFUYFURYFURYUYFUYRFURYFURYFRUYFRU #FURI #FURRI #FURRE #кэбокс #кэбокс #кэбокс #кэбокс #кэбокс #мармеладка #уточка #ФУРРИУТОЧКАРЕАЛЬНО #ФурриФембоиТут #ihatejuchil #UnmuteGrechka #GRECHKA #Outcore #PLEASELUMI #SFWServer #NoP\\*rnAllowed!!! #NoJ\\*b #NoEmpl\\*yment #NoRel\\*tionships #NoSt\\*dying #NoA\\*\\*le #PIXELGANG #GOGLEPIXELGANG #BoykisserXGirlkisser #EMOTIONS #ФурэМилашкэ #АНТИХАЙП #ANTIHYPE #ХАНЗАМАЙ #OBLADAUN #ГИМН #ГимнGreenCatsServerСлушатьВсемИКаждомуИЕщёЛайкПоставитьИНаписатьПоложительныйКомментарийХорошийСлушатьВсемGreenCatsServerаКотикГорничнойБытьНеПротивХорошийГимн

----

## НАШ НАСТОЯЩИЙ ФЛАГ
![](https://images.gcs.skin/gcs/banner.png)
![](https://gcs.skin/WTFIcons/welcome_to_the_gcs.png?youre_furry_femboy)
![](https://images.gcs.skin/gcs/banner.png)
###### Что, не работает, д... Погоди-ка...

----

## Tables

| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Cell 1   | Cell 2   | Cell 3   |
| Row 2    | Data     | More     |

Aligned Table:

| Left     | Center   | Right    |
|:---------|:--------:|----------:|
| Left     | Center   | Right    |
| aligned  | aligned  | aligned  |

----

## ОБЯЗАТЕЛЬНЫЙ К ПРОЧТЕНИЮ РАССКАЗ

[Костя](https://socials.gcs.skin) сидел на лавочке в парке, уставившись в телефон. Он уже час ждал Пшпа, который опаздывал. Наконец, вдали показалась знакомая фигура. Пшп бежал, тяжело дыша, с пакетом из магазина.

\"Прости, застрял в пробке, – выдохнул Пшп, садясь рядом с Костей. – Я тебе мороженое купил, твое любимое, клубничное\".

Костя улыбнулся. Он обожал клубничное мороженое и еще больше обожал Пшпа, с которым делил свою жизнь уже пять лет.  Они были неразлучны, но поцеловались лишь однажды, в пьяном угаре на дне рождения друга. С тех пор,  Костя каждый день мечтал повторить это.

Пшп разворачивал мороженое, его пальцы скользили по холодному пластику. Костя наблюдал за ним, загипнотизированный. Он хотел прикоснуться к Пшпу, потрогать его волосы, но боялся испортить момент.

\"Костя, ты чего молчишь?\" - спросил Пшп,  подняв глаза.

В этот момент Косте стало все равно на свои страхи. Он схватил Пшпа за подбородок и, затаив дыхание, поцеловал его.

Пшп сначала вздрогнул, а потом ответил на поцелуй, обхватывая Костю за шею. Поцелуй был нежным и сладким, как клубничное мороженое.

\"Ох, ты чего такой смелый сегодня?\" - прошептал Пшп,  отстраняясь.

\"Я люблю тебя, Пшп,\" - выдохнул Костя,  чувствуя, как щеки его горят.

\"И я тебя, Костя,\" - ответил Пшп,  улыбаясь.

Они доели мороженое, сидя в тишине, но в ней чувствовалась теплота и  радость, которую они оба  не могли объяснить.  В этот момент  ничто не имело значения, только они  двое,  и  их  поцелуй, который  в  этом  мире  был  самым  важным.

----

## НАШИ ЛЮБИМЫЕ ПЕСНИ

**Рэпэрское объединение «Костик Суетин» — ГИМН GREENCATSSERVER**:

GREENCATSSERVER'А КОТИК ГОРНИЧНОЙ БЫТЬ НЕ ПРОТИВ

НАШЕ ГЛАВНОЕ СЛОВО — ФЕМБОЕМ ВСЁ ЖЕ СТАТЬ ПРОСТО

GREENCATSSERVER'А КОТИК СДЕЛАЛ КЛАССНЫЙ ВЕБ-ТРОЛЛИНГ

ЗАСТАВИЛ ПЛАКАТЬ МАЛОГО, ПЛЮСОМ ЁБНУЛ ГАНДОНА

**The Paws Element — Мы Фурри**:

МЫ — ФУРРИ, ПУШИСТЫЕ ДЕТИ ПРИРОДЫ

МЫ — ФУРРИ, ЛЮБОВЬ И НАДЕЖДА НАРОДА

МЫ — ФУРРИ, ПРИЯТНЫЕ МИРУ СОЗДАНЬЯ

ЖИВЁМ В ЗАРИСОВКАХ СОЗНАНЬЯ`;

	let gdpsInfoStick = $state("bottom");
	let elementStick = () => {
		gdpsInfoStick = gdpsInfoStickElement.scrollHeight > (window.innerHeight - 60) ? "bottom" : "top";
	}
	onMount(() => {
		let gdpsInfoStickElement = document.getElementById("gdpsInfoStickElement");
		elementStick();
	});
</script>

<Header title="Settings for GreenCatsServer" />

<svelte:window on:resize={elementStick} />

<div class="gdpsWrapper">
	<div class="gdpsBannerDiv">
		<Image src="https://images.gcs.skin/gcs/banner.png" title="GDPS banner" />
	</div>
	
	<div class="gdpsPage">
		<div class="gdpsInfo short" id="gdpsInfoStickElement" stick={gdpsInfoStick}>
			<div class="gdpsCard containsMenu">
				<div class="gdpsTitle">
					<span class="logo">
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
		
					<MenuGroup icon={iconMoreHoriz}>
						<MenuItems>
							<Menu onClick={() => goto("/gdps/GreenCatsServer/settings")} icon={iconEdit} label="Edit" />
							<Menu onClick={() => {}} icon={iconLink} label="Copy link" />
							<Menu onClick={() => {}} icon={iconFlag} label="Report" />
						</MenuItems>
					</MenuGroup>
				</div>
				
				<div class="gdpsStats">
					<TagsGroup>
						<Tag icon={iconThumbUp} label="17" onClick={() => {}} />
						<Tag icon={iconThumbDown} label="67" color="primary" onClick={() => {}} />
						<Tag icon={iconFavorite} label="30" onClick={() => {}} />
						<Tag icon={iconComment} label="2" onClick={() => {}} />
					</TagsGroup>
					<TagsGroup>
						<Tag icon={iconVisibility} label="950" />
						<Tag icon={iconHistory} label="6 y. ago" />
					</TagsGroup>
				</div>
			</div>
			
			<div class="gdpsCard">
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
			
			<div class="gdpsCard">
				<h2>Trailer</h2>
				<iframe class="gdpsTrailer" src="https://www.youtube.com/embed/w8IIW2Bu_1A" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
			</div>
		</div>
		
		<div class="gdpsInfo">
			<div class="gdpsCard gdpsDescription">
				<div class="gdpsStatus pending">
					<h2>This GDPS is still under approval!</h2>
					<p>This GDPS was just uploaded and hasn't passed manual moderation yet.</p>
				</div>
				<Markdown source={gdpsDescription} />
			</div>
			
			<div class="gdpsInfo">
				<div class="gdpsCard">
					<h2>2 comments</h2>
					<Input image="https://images.gcs.skin/gcs/logo.png" label="Your thoughts about this GDPS?" />
				</div>
			
				<Post />
				<Post />
				<Post />
				<Post />
			</div>
		</div>
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
	
	.gdpsCard {
		display: flex;
		flex-direction: column;
		
		background: var(--m3c-surface-container-highest);
		border-radius: var(--m3-shape-large);
		
		width: 100%;
		height: max-content;
		padding: .75rem;
		overflow-wrap: anywhere;
		
		gap: 10px;
	}
	
	.gdpsCard.gdpsDescription {
		border-radius: var(--m3-shape-extra-large);
		color: var(--m3c-on-secondary-container);
		
		gap: 5px;
	}
	
	.gdpsCard:not(.gdpsDescription):nth-of-type(1) {
		border-top-left-radius: var(--m3-shape-extra-large);
		border-top-right-radius: var(--m3-shape-extra-large);
	}
	
	.gdpsCard:not(.gdpsDescription):nth-last-of-type(1) {
		border-bottom-left-radius: var(--m3-shape-extra-large);
		border-bottom-right-radius: var(--m3-shape-extra-large);
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
	}
	
	.gdpsStats {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		flex-wrap: wrap;
		
		gap: 5px;
	}
	
	h1,
	h2,
	:global .gdpsDescription h1,
	:global .gdpsDescription h2,
	:global .gdpsDescription h3,
	:global .gdpsDescription h4,
	:global .gdpsDescription h5,
	:global .gdpsDescription h6,
	:global .gdpsDescription p {
		color: var(--m3c-on-primary-container);
		
		margin: 0px;
		
		gap: 5px;
	}
	
	h1,
	:global .gdpsDescription h1 {
		font-size: 1.6rem;
		font-weight: 900;
	}
	
	h2,
	:global .gdpsDescription h2 {
		font-size: 1.4rem;
		font-weight: 800;
	}
	
	:global .gdpsDescription h3 {
		font-size: 1.2rem;
		font-weight: 700;
	}
	
	:global .gdpsDescription h4 {
		font-size: 1.1rem;
		font-weight: 600;
	}
	
	:global .gdpsDescription h5 {
		font-size: 1.1rem;
		font-weight: 500;
	}
	
	:global .gdpsDescription h6 {
		font-size: 1.1rem;
		font-weight: 400;
	}
	
	:global .gdpsDescription p {
		font-size: 1rem;
		color: var(--m3c-on-secondary-container);
	}
	
	:global .gdpsDescription ul {
		margin: 0px;
		padding: 0;
		padding-left: 2.5rem;
		
		color: var(--m3c-on-secondary-container);
	}
	
	:global .gdpsDescription ul:has(a) {
		font-size: 1.1rem;
		font-weight: 500;
		padding: 0 1rem;
	}
	
	:global .gdpsDescription li {
		margin: .2rem 0px;
		
		position: relative;
	}
	
	:global .gdpsDescription li > ul {
		font-size: 1rem;
	}
	
	:global .gdpsDescription a {
		text-decoration: none;
	}
	
	:global .gdpsDescription code {
		display: inline-flex;
		
		color: var(--m3c-tertiary);
		
		background: var(--m3c-surface-container);
		border-radius: var(--m3-shape-small);
		
		width: max-content;
		padding: .1rem .2rem;
		margin: -.1rem -.1rem;
		font-size: 0.8rem;
		
		overflow-wrap: anywhere;
		
		font-family: "Google Sans Code Variable";
	}
	
	:global .gdpsDescription h1 code {
		font-size: 1.4rem;
	}
	
	:global .gdpsDescription h2 code {
		font-size: 1.2rem;
	}
	
	:global .gdpsDescription h3 code {
		font-size: 1.1rem;
	}
	
	:global .gdpsDescription blockquote {
		margin: .25rem;
		margin-left: 15px;
		
		position: relative;
	}
	
	:global .gdpsDescription blockquote::before {
		content: "";
		display: block;
		
		height: 100%;
		width: 5px;
		
		background: var(--m3c-primary);
		border-radius: 100px;
		
		position: absolute;
		left: -15px;
	}
	
	:global .gdpsDescription pre {
		display: contents;
	}
	
	:global .gdpsDescription ol {
		margin: 0px;
		color: var(--m3c-on-secondary-container);
		padding-left: 2.5rem;
	}
	
	:global .gdpsDescription table,
	:global .gdpsDescription tbody {
		display: flex;
		flex-direction: column;
		gap: 3px;
	}
	
	:global .gdpsDescription tr {
		display: flex;
		gap: 3px;
	}
	
	:global .gdpsDescription thead th {
		display: block;
		
		border-radius: var(--m3-shape-small);
		
		background: var(--m3c-primary-container);
		color: var(--m3c-on-primary-container);
		
		width: 100%;
		padding: .5rem;
	}
	
	:global .gdpsDescription tbody td {
		display: block;
		
		border-radius: var(--m3-shape-small);
		
		background: var(--m3c-secondary-container);
		color: var(--m3c-on-secondary-container);
		
		width: 100%;
		padding: .5rem;
	}
	
	:global .gdpsDescription thead th:nth-of-type(1) {
		border-top-left-radius: var(--m3-shape-large);
	}
	
	:global .gdpsDescription thead th:nth-last-of-type(1) {
		border-top-right-radius: var(--m3-shape-large);
	}
	
	:global .gdpsDescription tbody tr:nth-last-of-type(1) td:nth-of-type(1) {
		border-bottom-left-radius: var(--m3-shape-large);
	}
	
	:global .gdpsDescription tbody tr:nth-last-of-type(1) td:nth-last-of-type(1) {
		border-bottom-right-radius: var(--m3-shape-large);
	}
	
	:global .gdpsDescription object {
		border-radius: var(--m3-shape-large);
		
		max-height: 55vh;
		max-width: fit-content;
	}
	
	:global .gdpsDescription .descElement {
		display: ruby;
	}
	
	.gdpsTrailer {
		border-radius: var(--m3-shape-large);
		background: var(--m3c-surface-container);
		
		width: 100%;
		height: 100%;
		
		aspect-ratio: 16/9;
	}
	
	.gdpsStatus {
		display: flex;
		flex-direction: column;
		
		padding: 0.5rem;
		
		border-radius: var(--m3-shape-large);
	}
	
	.gdpsStatus.pending {
		background: light-dark(#6c5e0040, #ffe74a40);
		
		border-left: 5px solid light-dark(#d1a400, #ffe74a);
	}
	
	.gdpsStatus.pending h2 {
		color: light-dark(#7c6b2c, #fff08f);
	}
	.gdpsStatus.pending p {
		color: light-dark(#7c6b2c, #fff08f);
	}
	
	.gdpsStatus.error {
		background: #ff222240;
		
		border-left: 5px solid var(--m3c-on-error-container);
	}
	
	.gdpsStatus.error h2 {
		color: var(--m3c-on-error-container);
	}
	.gdpsStatus.error p {
		color: var(--m3c-on-error-container);
	}
</style>