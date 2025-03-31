<script lang="ts">
	import { pin, wifi, wine, warning, walk } from 'ionicons/icons';
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';
</script>

<svelte:head>
	<title>Ionic Companion - Cards</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Card" />
			</ion-buttons>
			<ion-title>Card</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen>
		<ion-card>
			<ion-card-header>
				<ion-card-subtitle>Card Subtitle</ion-card-subtitle>
				<ion-card-title>Card Title</ion-card-title>
			</ion-card-header>

			<ion-card-content>
				Keep close to Nature's heart... and break clear away, once in awhile, and climb a mountain
				or spend a week in the woods. Wash your spirit clean.
			</ion-card-content>
		</ion-card>

		<ion-card>
			<ion-item>
				<ion-icon icon={pin} slot="start" />

				<ion-label>ion-item in a card, icon left, button right</ion-label>
				<ion-button fill="outline" slot="end">View</ion-button>
			</ion-item>

			<ion-card-content>
				This is content, without any paragraph or header tags, within an ion-card-content element.
			</ion-card-content>
		</ion-card>

		<ion-card>
			<ion-item href="/components/tabs/:tab" class="activated">
				<ion-icon icon={wifi} slot="start" />
				<ion-label>Card Link Item 1 .activated</ion-label>
			</ion-item>

			<ion-item href="/components/Button">
				<ion-icon icon={wine} slot="start" />
				<ion-label>Card Link Item 2</ion-label>
			</ion-item>

			<ion-item class="activated">
				<ion-icon icon={warning} slot="start" />
				<ion-label>Card Button Item 1 .activated</ion-label>
			</ion-item>

			<ion-item>
				<ion-icon icon={walk} slot="start" />
				<ion-label>Card Button Item 2</ion-label>
			</ion-item>
		</ion-card>

		<ion-card>
			<img src="/assets/img/madison.jpg" alt="madison" />
			<ion-card-header>
				<ion-card-subtitle>Destination</ion-card-subtitle>
				<ion-card-title>Madison, WI</ion-card-title>
			</ion-card-header>
			<ion-card-content>
				Founded in 1829 on an isthmus between Lake Monona and Lake Mendota, Madison was named the
				capital of the Wisconsin Territory in 1836.
			</ion-card-content>
		</ion-card>
	</ion-content>
</IonPage>
