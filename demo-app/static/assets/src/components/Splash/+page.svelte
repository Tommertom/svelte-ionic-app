<script lang="ts">
	import { scale } from 'svelte/transition';
	import { elasticInOut } from 'svelte/easing';

	import { goto } from '$app/navigation';

	import { onMount } from 'svelte';
	import { showMenu } from '$lib/services/menu';
	showMenu.set(false);

	onMount(() => {
		let splitpane: HTMLIonSplitPaneElement | null;
		splitpane = document.querySelector('ion-split-pane');
		if (splitpane != null) splitpane.disabled = true;

		setTimeout(() => {
			if (splitpane != null) splitpane.disabled = false;
			navigate('/components/Slides');
		}, 4000);
	});

	function navigate(url: string) {
		showMenu.set(true);
		goto(url);
	}
</script>

<!-- routify:meta draft=true -->
<ion-content>
	<br />
	<br /> <br />
	<br />
	<br />
	<div class="ion-text-center">
		<img
			src="/assets/svelte-ionic-logo.png"
			alt="Great success"
			in:scale={{ duration: 1900, easing: elasticInOut }} />
		<br /><br /><br />
		<div in:scale={{ delay: 400, duration: 1900, easing: elasticInOut }}>Great success!</div>
	</div>
</ion-content>

<style>
	img {
		width: 60%;
		max-width: 90vw;
		max-height: 90vh;
	}

	div {
		font-size: 140%;
	}
</style>
