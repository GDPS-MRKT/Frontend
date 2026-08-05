<script>
	import { goto } from '$app/navigation';
	import { Icon, Button } from "m3-svelte";
	import Image from "./Image.svelte";
</script>

<div class="m3-layer gdpsSmall" on:click={() => goto("/gdps/GreenCatsServer")}>
	<div class="gdpsTitle">
		<span class="smallGDPSlogo">
			<Image src="https://images.gcs.skin/gcs/logo.png" title="GDPS logo" />
		</span>
		
		<div class="gdpsName">
			<h1>GreenCatsServer</h1>
			<h3 on:click={() => goto("/profile/Sa1ntSosetHui")}>Sa1ntSosetHui</h3>
		</div>
	</div>
</div>

<style>
	.gdpsSmall {
		background: var(--m3c-secondary-container);
		
		padding: .75rem;
		--shape: var(--m3-shape-medium);
		border-radius: var(--shape);
		
		cursor: pointer;
		
		transition:
			border-radius var(--m3-easing-fast-spatial),
			box-shadow var(--m3-easing-fast),
			background-color var(--m3-easing-fast),
			color var(--m3-easing-fast);
	}
	
	.gdpsSmall:active {
		--shape: var(--m3-shape-small);
	}
	
	.gdpsSmall:nth-of-type(1) {
		border-top-left-radius: var(--m3-shape-large-increased);
		border-top-right-radius: var(--m3-shape-large-increased);
	}
	
	.gdpsSmall:nth-last-of-type(1) {
		border-bottom-left-radius: var(--m3-shape-large-increased);
		border-bottom-right-radius: var(--m3-shape-large-increased);
	}
	
	.gdpsTitle {
		display: flex;
		align-items: center;
		
		gap: 7px;
	}
	
	.gdpsTitle h1 {
		font-size: 1.2rem;
		color: var(--m3c-on-primary-container);
	}
	
	.gdpsTitle h3 {
		font-weight: 400;
		font-size: 14px;
		margin: 0px;
		
		color: var(--m3c-on-secondary-container);
	}
	
	.gdpsTitle .smallGDPSlogo {
		max-height: 40px;
		max-width: 40px;
		width: 100%;
		height: 100%;
		
		border-radius: var(--m3-shape-small);
		overflow: hidden;
		
		aspect-ratio: 1/1;
	}
</style>