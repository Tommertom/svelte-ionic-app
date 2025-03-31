<script lang="ts">
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';
</script>

<svelte:head>
	<title>Ionic Companion - Spinner</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Spinner" />
			</ion-buttons>
			<ion-title>Spinner</ion-title>
		</ion-toolbar>
	</ion-header>
	<ion-content>
		<ion-list>
			<ion-item>
				<ion-label>Default</ion-label>
				<ion-spinner />
			</ion-item>

			<ion-item>
				<ion-label>Lines</ion-label>
				<ion-spinner name="lines" />
			</ion-item>

			<ion-item>
				<ion-label>Lines Small</ion-label>
				<ion-spinner name="lines-small" />
			</ion-item>

			<ion-item>
				<ion-label>Dots</ion-label>
				<ion-spinner name="dots" />
			</ion-item>

			<ion-item>
				<ion-label>Bubbles</ion-label>
				<ion-spinner name="bubbles" />
			</ion-item>

			<ion-item>
				<ion-label>Circles</ion-label>
				<ion-spinner name="circles" />
			</ion-item>

			<ion-item>
				<ion-label>Crescent</ion-label>
				<ion-spinner name="crescent" />
			</ion-item>

			<ion-item>
				<ion-label>Paused</ion-label>
				<ion-spinner paused />
			</ion-item>

			<ion-item>
				<ion-label>Primary</ion-label>
				<ion-spinner color="primary" />
			</ion-item>

			<ion-item>
				<ion-label>Secondary</ion-label>
				<ion-spinner color="secondary" />
			</ion-item>

			<ion-item>
				<ion-label>Tertiary</ion-label>
				<ion-spinner color="tertiary" />
			</ion-item>
		</ion-list>
	</ion-content>
</IonPage>
