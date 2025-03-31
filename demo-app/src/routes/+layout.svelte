<script lang="ts">
	import { dev } from '$app/environment';
	import { preloadCode } from '$app/navigation';

	import { pwaStatusStream, type PWAStatus } from '$lib/services/pwa';

	import Menu from '$lib/components/Menu.svelte';

	import { setupIonicBase } from 'ionic-svelte';

	/* Theme variables */
	import '../theme/variables.css';
	import 'ionic-svelte/components/all';

	setupIonicBase();

	pwaStatusStream.subscribe((status: PWAStatus) => {
		console.log('PWA status', status);

		if (status.updateFunction) {
			console.log('PWA updating itself in 4 secs......');
			setTimeout(() => {
				status.updateFunction();
			}, 4000);
		}
	});

	// Aggressive prefetching for faster rendering
	if (!dev) {
		preloadCode();
	}
</script>

<ion-app>
	<ion-split-pane content-id="main">
		<Menu />
		<div class="ion-page" id="main">
			<slot />
		</div>
	</ion-split-pane>
</ion-app>
