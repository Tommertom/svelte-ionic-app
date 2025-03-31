<script lang="ts">
	import ModalExtra from '$lib/components/ModalExtra.svelte';
	import PopoverExtra from '$lib/components/PopoverExtra.svelte';
	import {
		alertController,
		modalController,
		loadingController,
		toastController,
		pickerController,
		actionSheetController,
		popoverController
	} from 'ionic-svelte';

	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';

	const showActionSheet = async () => {
		const options = {
			header: 'Albums',
			buttons: [
				{
					text: 'Delete',
					role: 'destructive',
					handler: () => {
						console.log('Delete clicked');
					}
				},
				{
					text: 'Share',
					handler: () => {
						console.log('Share clicked');
					}
				},
				{
					text: 'Play',
					handler: () => {
						console.log('Play clicked');
					}
				},
				{
					text: 'Favorite',
					handler: () => {
						console.log('Favorite clicked');
					}
				},
				{
					text: 'Cancel',
					role: 'cancel',
					handler: () => {
						console.log('Cancel clicked');
					}
				}
			]
		};
		const actionsheet = await actionSheetController.create(options);

		actionsheet.present();
	};
</script>

<svelte:head>
	<title>Ionic Companion - Action Sheet</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Actionsheet" />
			</ion-buttons>
			<ion-title>Action sheet</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen class="ion-padding">
		<ion-button expand="block" on:click={showActionSheet}> Click me! </ion-button>
	</ion-content>
</IonPage>
