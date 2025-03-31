<script lang="ts">
	import { repeat } from 'ionicons/icons';
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';

	// code taken from https://petercoding.com/ionic/2019/05/06/implementing-reorder-in-ionic4/
	let reorderGroup;
	const items = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

	const toggleReorder = () => {
		reorderGroup.disabled = !reorderGroup.disabled;
	};

	const reorderEvent = ({ detail }) => {
		console.log('Reorder detail', detail);
		console.log(`Moving item from ${detail.from} to ${detail.to}`);
		const itemMove = items.splice(detail.from, 1)[0];
		items.splice(detail.to, 0, itemMove);
		console.log('New list of items ', items);
		detail.complete();
	};
</script>

<svelte:head>
	<title>Ionic Companion - Reorder</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Reorder" />
			</ion-buttons>
			<ion-title>Reorder</ion-title>
			<ion-buttons slot="primary">
				<ion-button on:click={toggleReorder}>Toggle</ion-button>
			</ion-buttons>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen>
		<ion-list>
			<ion-list-header>Reorder Icon</ion-list-header>
			<ion-reorder-group bind:this={reorderGroup} on:ionItemReorder={reorderEvent}>
				<ion-item>
					<ion-label>Item 1</ion-label>
					<ion-reorder slot="end" />
				</ion-item>

				<ion-item>
					<ion-label>Item 2</ion-label>
					<ion-reorder slot="end" />
				</ion-item>

				<ion-item>
					<ion-label>Item 3</ion-label>
					<ion-reorder slot="end" />
				</ion-item>

				<ion-item>
					<ion-label>Item 4</ion-label>
					<ion-reorder slot="end" />
				</ion-item>

				<ion-list-header>Custom Reorder Icon</ion-list-header>
				<ion-item>
					<ion-label>Item 5</ion-label>
					<ion-reorder slot="start">
						<ion-icon icon={repeat} />
					</ion-reorder>
				</ion-item>

				<ion-item>
					<ion-label>Item 6</ion-label>
					<ion-reorder slot="start">
						<ion-icon icon={repeat} />
					</ion-reorder>
				</ion-item>

				<ion-item>
					<ion-label>Item 7</ion-label>
					<ion-reorder slot="start">
						<ion-icon icon={repeat} />
					</ion-reorder>
				</ion-item>

				<ion-list-header>Reorder Item</ion-list-header>
				<ion-reorder>
					<ion-item>
						<ion-label>Item 8</ion-label>
					</ion-item>
				</ion-reorder>

				<ion-reorder>
					<ion-item>
						<ion-label>Item 9</ion-label>
					</ion-item>
				</ion-reorder>

				<ion-reorder>
					<ion-item>
						<ion-label>Item 10</ion-label>
					</ion-item>
				</ion-reorder>
			</ion-reorder-group>
		</ion-list>
	</ion-content>
</IonPage>
