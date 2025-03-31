<script lang="ts">
	import { onMount } from 'svelte';
	import { sunny, brush, thermometer, contrast } from 'ionicons/icons';
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';

	let dualRange;

	onMount(() => {
		dualRange.value = { lower: 33, upper: 60 };
	});
</script>

<svelte:head>
	<title>Ionic Companion - Range</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Range" />
			</ion-buttons>
			<ion-title>Range</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen>
		<ion-list>
			<ion-list-header>Adjust Display</ion-list-header>

			<ion-item>
				<ion-range value="20">
					<ion-icon slot="start" size="small" icon={sunny} />
					<ion-icon slot="end" icon={sunny} />
				</ion-range>
			</ion-item>

			<ion-item>
				<ion-range min="-200" max="200" pin color="secondary">
					<ion-icon slot="start" size="small" icon={contrast} />
					<ion-icon slot="end" icon={contrast} />
				</ion-range>
			</ion-item>

			<ion-item>
				<ion-range bind:this={dualRange} dual-knobs pin color="dark">
					<ion-icon slot="start" size="small" icon={brush} />
					<ion-icon slot="end" icon={brush} />
				</ion-range>
			</ion-item>

			<ion-item>
				<ion-range min="1000" max="2000" step="100" value="1400" snaps color="danger">
					<ion-icon slot="start" size="small" color="danger" icon={thermometer} />
					<ion-icon slot="end" color="danger" icon={thermometer} />
				</ion-range>
			</ion-item>
		</ion-list>
	</ion-content>
</IonPage>
