<script lang="ts">
	import ModalExtra from '$lib/components/ModalExtra.svelte';

	import { alertController, modalController } from 'ionic-svelte';

	import SourceButton from '$lib/components/SourceButton.svelte';

	import Music from '$lib/components/Music.svelte';
	import { IonPage } from 'ionic-svelte';

	let inlineModalOpen = false;
	let breakpoints = [0, 0.5, 1];

	const inlineModalDismissed = (val) => {
		console.log('inlineModalDismissed dismissed', val);
		inlineModalOpen = false;
	};

	const showAlert = async (options) => {
		const alert = await alertController.create(options);
		alert.present();
	};

	const showModalController = async () => {
		const options = {
			header: 'OOPS!',
			subHeader: 'broken',
			message:
				'Opening modal with modalcontroller does no longer work as of Ionic7 - needs debugging',
			buttons: ['OK']
		};

		return showAlert(options);

		// const modal = await modalController.create({
		// 	component: ModalExtra,
		// 	componentProps: {
		// 		firstName: 'Douglas',
		// 		lastName: 'Adams',
		// 		middleInitial: 'N'
		// 	},
		// 	showBackdrop: true,
		// 	backdropDismiss: false
		// });

		// modal.onDidDismiss().then((value) => {
		// 	console.log('Dismissed the modal', value);
		// 	if (value.role === 'backdrop') console.log('Backdrop clicked');
		// });

		// await modal.present();
	};
</script>

<svelte:head>
	<title>Ionic Companion - Modals</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Modal" />
			</ion-buttons>
			<ion-title>Modals</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen class="ion-padding">
		<h1>Click me stuff below!</h1>
		<ion-button expand="block" on:click={showModalController}
			>Show modal - via controller</ion-button>
		<ion-button
			expand="block"
			on:click={() => {
				inlineModalOpen = true;
			}}>Show modal - via inline & as sheet</ion-button>

		<ion-modal
			is-open={inlineModalOpen}
			initial-breakpoint="0.5"
			{breakpoints}
			on:ionModalDidDismiss={inlineModalDismissed}>
			<ion-content>
				<br /><br /><br />
				<ion-button
					expand="block"
					on:click={() => {
						inlineModalOpen = false;
					}}>
					Close modal
				</ion-button>
				<Music />
			</ion-content>
		</ion-modal>
	</ion-content>
</IonPage>
