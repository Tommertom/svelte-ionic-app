<script lang="ts">
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';
</script>

<svelte:head>
	<title>Ionic Companion - Progressbar</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="ProgressBar" />
			</ion-buttons>
			<ion-title>Progress Bar</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content class="outer-content">
		<!-- Default Progressbar -->
		<ion-list>
			<ion-list-header>
				<ion-label>Default</ion-label>
			</ion-list-header>
			<ion-progress-bar />
		</ion-list>

		<ion-list>
			<ion-list-header>
				<ion-label>Default at 50%</ion-label>
			</ion-list-header>
			<ion-progress-bar value={0.5} />
		</ion-list>

		<ion-list>
			<ion-list-header>
				<ion-label>Colorized</ion-label>
			</ion-list-header>
			<!-- Colorize Progressbar -->
			<ion-progress-bar color="primary" value={0.5} />
			<ion-progress-bar color="secondary" value={0.5} />

			<ion-list-header>
				<ion-label>Indeterminate</ion-label>
			</ion-list-header>
			<ion-progress-bar type="indeterminate" />

			<ion-list-header>
				<ion-label>Indeterminate (reversed)</ion-label>
			</ion-list-header>
			<ion-progress-bar type="indeterminate" reversed={true} />

			<ion-list-header>
				<ion-label>Buffer</ion-label>
			</ion-list-header>
			<ion-progress-bar value={0.25} buffer={0.5} />
		</ion-list>
	</ion-content>
</IonPage>
