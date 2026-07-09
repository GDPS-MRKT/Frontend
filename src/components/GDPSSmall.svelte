<script>
	import { goto } from '$app/navigation';
	import { Icon, Button } from "m3-svelte";
</script>

<div class="m3-layer gdps">
	<div class="gdpsTitle">
		<span class="logo">
			<img src="https://images.gcs.skin/gcs/logo.png" alt="GDPS logo" />
		</span>
		
		<div class="gdpsName">
			<h1>GreenCatsServer</h1>
			<h3 on:click={() => goto("/profile/Sa1ntSosetHui")}>Sa1ntSosetHui</h3>
		</div>
	</div>
</div>

<style>
	.gdps {
		background: var(--m3c-secondary-container);
		
		padding: .75rem;
		border-radius: var(--m3-shape-small);
		
		cursor: pointer;
	}
	
	.gdps:nth-of-type(1) {
		border-top-left-radius: var(--m3-shape-large-increased);
		border-top-right-radius: var(--m3-shape-large-increased);
	}
	
	.gdps:nth-last-of-type(1) {
		border-bottom-left-radius: var(--m3-shape-large-increased);
		border-bottom-right-radius: var(--m3-shape-large-increased);
	}
	
	h1 {
		font-size: 1.2rem;
		color: var(--m3c-on-primary-container);
	}
	
	h3 {
		font-weight: 400;
		font-size: 14px;
		margin: 0px;
		
		color: var(--m3c-on-secondary-container);
	}
	
	.logo {
		height: 40px;
	}
	
	.logo img {
		height: 40px;
		border-radius: var(--m3-shape-small);
	}
	
	.gdpsTitle {
		display: flex;
		align-items: center;
		
		gap: 7px;
	}
</style>