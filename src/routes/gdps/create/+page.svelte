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
	
	import iconArrowForward from "@ktibow/iconset-material-symbols/arrow-forward-ios-rounded";
	
	import CreationCard from "../../../lib/assets/mrkt_gdps.svelte";
	
	const pageSizes = ["30rem", "100%"];
	
	let currentPage = $state(0);
	let currentPageSize = $state(` --height: ${pageSizes[currentPage]};`);
	
	function nextPage() {
		currentPage++;
		currentPageSize = `--height: ${pageSizes[currentPage]};`;
	}
	
	onMount(() => {
		let gdpsCreationPage = document.getElementById("gdpsCreationPage");
	});
</script>

<Header title="Create GDPS" />

<div class="gdpsCreationWrapper">
	<div class="gdpsCreationPagesDiv" id="gdpsCreationPage" style={currentPageSize}>
		<div class="gdpsCreationPage">
			<span class="gdpsCreationImage">
				<svelte:component this={CreationCard} />
			</span>
			
			<h1>Welcome to MRKT!</h1>
			<h2>This page will guide you on publishing GDPS to MRKT.</h2>
			
			<Button onclick={nextPage}>
				<Icon icon={iconArrowForward} /> Continue
			</Button>
		</div>
		
		<div class="gdpsCreationPage">
			<span class="gdpsCreationImage">
				<svelte:component this={CreationCard} />
			</span>
			
			<h1>Welcome to MRKT!</h1>
			<h2>This page will guide you on publishing GDPS to MRKT.</h2>
			
			<Button onclick={nextPage}>
				<Icon icon={iconArrowForward} /> Continue
			</Button>
		</div>
	</div>
</div>

<style>
	.gdpsCreationWrapper {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		
		width: 100%;
		height: 100%;
		
		overflow: hidden;
		
		gap: 10px;
	}
	
	.gdpsCreationPagesDiv {
		display: flex;
		justify-content: center;
		align-items: center;
		
		padding: .75rem;
		background: var(--m3c-surface-container-highest);
		border-radius: var(--m3-shape-extra-large);
		
		width: 50rem;
		height: var(--height, 100%);
		
		transition: var(--m3-easing-slow-spatial);
	}
	
	.gdpsCreationImage {
		width: 17rem;
	}
	
	.gdpsCreationPage {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		
		gap: 10px;
		
		width: 50rem;
		height: 100%;
		
		text-align: center;
	}
	
	h1 {
		color: var(--m3c-on-primary-container);
		margin: 0px;
		font-size: 1.6rem;
		font-weight: 900;
	}
	
	h2 {
		color: var(--m3c-on-primary-container);
		font-size: 1.3rem;
		font-weight: 500;
		margin: 0px;
	}
</style>