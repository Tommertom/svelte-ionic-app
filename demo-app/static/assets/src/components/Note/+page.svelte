<script>
	import { IonPage } from 'ionic-svelte';
	import SourceButton from '$lib/components/SourceButton.svelte';

	const ionViewWillEnter = () => {
		console.log('Note:ionViewWillEnter');
	};

	const ionViewDidEnter = () => {
		console.log('Note:ionViewDidEnter');
	};

	const ionViewWillLeave = () => {
		console.log('Note:ionViewWillLeave');
	};

	const ionViewDidLeave = () => {
		console.log('Note:ionViewDidLeave');
	};
</script>

<svelte:head>
	<title>Ionic Companion - Notes</title>
</svelte:head>

<IonPage {ionViewWillEnter} {ionViewDidEnter} {ionViewWillLeave} {ionViewDidLeave}>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Note" />
			</ion-buttons>
			<ion-title>Note</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen>
		<ion-list>
			<ion-list-header>Basic</ion-list-header>
			<ion-grid>
				<ion-row>
					<ion-col>
						<ion-note>Default</ion-note>
					</ion-col>
					<ion-col>
						<ion-note color="primary">Primary</ion-note>
					</ion-col>
					<ion-col>
						<ion-note color="secondary">Secondary</ion-note>
					</ion-col>
					<ion-col>
						<ion-note color="tertiary">Tertiary</ion-note>
					</ion-col>
				</ion-row>
				<ion-row>
					<ion-col>
						<ion-note color="success">Success</ion-note>
					</ion-col>
					<ion-col>
						<ion-note color="warning">warning</ion-note>
					</ion-col>
					<ion-col>
						<ion-note color="danger">Danger</ion-note>
					</ion-col>
					<ion-col>
						<ion-note color="dark">Dark</ion-note>
					</ion-col>
				</ion-row>
			</ion-grid>

			<ion-list-header>List Notes</ion-list-header>
			<ion-item>
				<ion-label>Default</ion-label>
				<ion-note slot="end">11</ion-note>
			</ion-item>

			<ion-item>
				<ion-label>Primary</ion-label>
				<ion-note slot="end" color="primary">22</ion-note>
			</ion-item>

			<ion-item>
				<ion-label>Secondary</ion-label>
				<ion-note slot="end" color="secondary">33</ion-note>
			</ion-item>

			<ion-item>
				<ion-label>Tertiary</ion-label>
				<ion-note slot="end" color="tertiary">44</ion-note>
			</ion-item>

			<ion-item>
				<ion-label>Success</ion-label>
				<ion-note slot="start" color="success">55</ion-note>
			</ion-item>

			<ion-item>
				<ion-label>Warning</ion-label>
				<ion-note slot="start" color="warning">66</ion-note>
			</ion-item>

			<ion-item>
				<ion-label>Danger</ion-label>
				<ion-note slot="start" color="danger">77</ion-note>
			</ion-item>

			<ion-item>
				<ion-label>Dark</ion-label>
				<ion-note slot="start" color="dark">88</ion-note>
			</ion-item>
		</ion-list>
	</ion-content>

	<style>
		ion-grid {
			padding-left: 9px;
		}
		ion-row {
			margin-bottom: 10px;
		}
	</style>
</IonPage>
