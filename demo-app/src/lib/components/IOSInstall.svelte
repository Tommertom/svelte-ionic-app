<script lang="ts">
	import { alertController, modalController } from 'ionic-svelte';

	const closeModal = async () => {
		modalController.dismiss();
	};

	const doneThat = async () => {
		const options = {
			header: 'Great!',
			subHeader: 'Thanks for install Ionic Svelte',
			message: 'The app should now be visible as icon on your home screen - somewhere....',
			buttons: [
				{
					text: 'Ok',
					handler: (data) => {
						console.log('Confirm Ok', data);
						closeModal();
					}
				}
			]
		};

		const alert = await alertController.create(options);
		alert.present();
	};

	// default code
	let isSafari = /^((?!chrome|android).)*safari/i.test(navigator.userAgent);
</script>

<svelte:head>
	<title>Welcom to install</title>
</svelte:head>

<ion-content fullscreen class="ion-padding">
	<br />
	<img src="/assets/svelte-ionic-logo.png" alt="Ionic Svelte" width="55%" />
	<h2>Hey there!</h2>
	{#if !isSafari}
		<br /><br />
		<h2>You are not running safari.</h2>
		<p>Open this site again with Safari.</p>
		<br />
		<p>Why? Safari on iPhone does the Add-to-Home-Screen correctly</p>
		<br /><br />
		<ion-button expand="block" on:click={closeModal}>Bummer - will do that!</ion-button>
	{/if}

	{#if isSafari}
		<p>Great! The next step is to add this site to your home screen.</p>

		<p>Select the share option in Safari and then select Add to Home Screen</p>
		<img src="/assets/img/safari-bar.png" alt="Safari Bar" />
		<br />
		<img width="60%" src="/assets/img/safari-share-options.png" alt="Safari Share Options" /><br />
		<ion-button expand="block" on:click={doneThat}>Yup - done that!</ion-button>
	{/if}
</ion-content>

<style>
	p {
		text-align: center;
	}
	h2 {
		text-align: center;
	}

	img {
		display: block;
		margin-left: auto;
		margin-right: auto;
	}
</style>
