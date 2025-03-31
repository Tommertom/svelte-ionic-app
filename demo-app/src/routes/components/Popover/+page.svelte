<script lang="ts">
	import PopoverExtra from '$lib/components/PopoverExtra.svelte';
	import { popoverController } from 'ionic-svelte';

	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';

	const showPopover = async (event) => {
		const popover = await popoverController.create({
			component: PopoverExtra,
			componentProps: {
				firstName: 'Douglas',
				lastName: 'Adams',
				middleInitial: 'N'
			},
			event
		});

		popover.onDidDismiss().then((value) => {
			console.log('Dismissed the popover', value);
			if (value.role === 'backdrop') console.log('Backdrop clicked');
		});

		await popover.present();
	};
</script>

<svelte:head>
	<title>Ionic Companion - Popovers</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Popover" />
			</ion-buttons>
			<ion-title>Popovers</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen class="ion-padding">
		<ion-button expand="block" on:click={showPopover}>Click me!</ion-button>
	</ion-content>
</IonPage>
