<script lang="ts">
	import { IonPage } from 'ionic-svelte';
	import SourceButton from '$lib/components/SourceButton.svelte';

	const ionViewWillEnter = () => {
		console.log('Page:ionViewWillEnter');
	};

	const ionViewDidEnter = () => {
		console.log('Page:ionViewDidEnter');
	};

	const ionViewWillLeave = () => {
		console.log('Page:ionViewWillLeave');
	};

	const ionViewDidLeave = () => {
		console.log('Page:ionViewDidLeave');
	};

	const ionPageSyntax = `...
  const ionViewWillEnter=
        ionViewDidEnter=
        ionViewWillLeave=
        ionViewDidLeave=console.log('We got an event!') 
  
  <IonPage {ionViewWillEnter} {ionViewDidEnter} {ionViewWillLeave} {ionViewDidLeave}>
  
  `;
</script>

<svelte:head>
	<title>Ionic Companion - Page</title>
</svelte:head>

<IonPage {ionViewWillEnter} {ionViewDidEnter} {ionViewWillLeave} {ionViewDidLeave}>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Page" />
			</ion-buttons>
			<ion-title>Page</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen class="ion-padding">
		<ion-card>
			<ion-card-header><h1>API specs for IonPage</h1></ion-card-header>
			<ion-card-content>
				This intends to show the working of the IonPage component. This components the lifecycle
				hooks and proper animation for a page shown in your app. The following lifecycle hooks are
				provided for:
				<br />
				<pre>
  ionViewWillEnter
  ionViewDidEnter
  ionViewWillLeave
  ionViewDidLeave
</pre>
				You can bind the hook using simple function binding.
				<pre>
  {ionPageSyntax}
</pre>

				Easy does it!
			</ion-card-content>
		</ion-card>
	</ion-content>
</IonPage>
