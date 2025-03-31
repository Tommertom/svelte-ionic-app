<script lang="ts">
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';
</script>

<svelte:head>
	<title>Ionic Companion - Buttons</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons collapse={true} slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Button" />
			</ion-buttons>
			<ion-title>Button</ion-title>
		</ion-toolbar>
	</ion-header>
	<ion-content fullscreen>
		<section>
			<header>Small Size</header>
			<ion-button size="small">Default</ion-button>
			<ion-button size="small" color="secondary">Secondary</ion-button>
			<ion-button size="small" color="tertiary">Tertiary</ion-button>
		</section>

		<section>
			<header>Default Size</header>
			<ion-button color="success">Success</ion-button>
			<ion-button color="warning">Warning</ion-button>
			<ion-button color="danger">Danger</ion-button>
		</section>

		<section>
			<header>Large Size</header>
			<ion-button size="large" color="light">Light</ion-button>
			<ion-button size="large" color="medium">Medium</ion-button>
			<ion-button size="large" color="dark">Dark</ion-button>
		</section>

		<section>
			<header>Block Width</header>
			<ion-button expand="block">A block button</ion-button>
		</section>

		<section class="full-width">
			<header>Full Width</header>
			<ion-button expand="full" color="secondary">A full-width button</ion-button>
		</section>
	</ion-content>
</IonPage>

<style>
	:root {
		--ion-safe-area-top: 20px;
		--ion-safe-area-bottom: 22px;
	}
	header {
		font-size: 11px;
		font-weight: 600;
		letter-spacing: 0.05em;
		margin-bottom: 1.25em;
		text-transform: uppercase;
	}
	section {
		margin-top: 1em;
		margin-bottom: 2.5em;
	}
	section:not(.full-width),
	.full-width > header {
		padding: 0 10px;
	}
</style>
