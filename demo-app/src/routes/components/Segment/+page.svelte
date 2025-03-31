<script lang="ts">
	import { pin, heart, call, logoIonic, logoTwitter, logoFacebook } from 'ionicons/icons';
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';

	const segmentChange = console.log;
	const segmentButtonChange = console.log;
</script>

<svelte:head>
	<title>Ionic Companion - Segment</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Segment" />
			</ion-buttons>
			<ion-title>Segment</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen>
		<ion-list-header>Default</ion-list-header>

		<!-- Label only -->
		<ion-segment on:ionChange={console.log} value="call" on:ionChange={segmentChange}>
			<ion-segment-button value="call">
				<ion-label>Call</ion-label>
			</ion-segment-button>
			<ion-segment-button value="favorite">
				<ion-label>Favorite</ion-label>
			</ion-segment-button>
			<ion-segment-button value="map">
				<ion-label>Map</ion-label>
			</ion-segment-button>
		</ion-segment>

		<!-- Icon only -->
		<ion-segment on:ionChange={console.log} color="secondary" value="heart">
			<ion-segment-button>
				<ion-icon icon={call} />
			</ion-segment-button>
			<ion-segment-button value="heart">
				<ion-icon icon={heart} />
			</ion-segment-button>
			<ion-segment-button>
				<ion-icon icon={pin} />
			</ion-segment-button>
		</ion-segment>

		<!-- Icon top -->
		<ion-segment on:ionChange={console.log} color="tertiary" value="favorite">
			<ion-segment-button>
				<ion-label>Call</ion-label>
				<ion-icon icon={call} />
			</ion-segment-button>
			<ion-segment-button value="favorite">
				<ion-label>Favorite</ion-label>
				<ion-icon icon={heart} />
			</ion-segment-button>
			<ion-segment-button>
				<ion-label>Map</ion-label>
				<ion-icon icon={pin} />
			</ion-segment-button>
		</ion-segment>

		<!-- Icon bottom -->
		<ion-segment on:ionChange={console.log} color="success" value="call">
			<ion-segment-button value="call" layout="icon-bottom">
				<ion-icon icon={call} />
				<ion-label>Call</ion-label>
			</ion-segment-button>
			<ion-segment-button layout="icon-bottom">
				<ion-icon icon={heart} />
				<ion-label>Favorite</ion-label>
			</ion-segment-button>
			<ion-segment-button layout="icon-bottom">
				<ion-icon icon={pin} />
				<ion-label>Map</ion-label>
			</ion-segment-button>
		</ion-segment>

		<ion-list-header>Scrollable</ion-list-header>

		<!-- Icon start -->
		<ion-segment on:ionChange={console.log} color="warning" value="call" scrollable>
			<ion-segment-button value="call" layout="icon-start">
				<ion-label>Call</ion-label>
				<ion-icon icon={call} />
			</ion-segment-button>
			<ion-segment-button layout="icon-start">
				<ion-label>Favorite</ion-label>
				<ion-icon icon={heart} />
			</ion-segment-button>
			<ion-segment-button layout="icon-start">
				<ion-label>Map</ion-label>
				<ion-icon icon={pin} />
			</ion-segment-button>
			<ion-segment-button layout="icon-start">
				<ion-label>Map</ion-label>
				<ion-icon icon={logoIonic} />
			</ion-segment-button>
			<ion-segment-button layout="icon-start">
				<ion-label>Map</ion-label>
				<ion-icon icon={logoTwitter} />
			</ion-segment-button>
			<ion-segment-button layout="icon-start">
				<ion-label>Map</ion-label>
				<ion-icon icon={logoFacebook} />
			</ion-segment-button>
		</ion-segment>

		<!-- Icon end -->
		<ion-segment on:ionChange={console.log} color="danger" value="call" scrollable>
			<ion-segment-button value="call" layout="icon-end">
				<ion-icon icon={call} />
				<ion-label>Call</ion-label>
			</ion-segment-button>
			<ion-segment-button layout="icon-end">
				<ion-icon icon={heart} />
				<ion-label>Favorite</ion-label>
			</ion-segment-button>
			<ion-segment-button layout="icon-end">
				<ion-icon icon={pin} />
				<ion-label>Map</ion-label>
			</ion-segment-button>
		</ion-segment>
	</ion-content>
</IonPage>

<style>
	ion-segment {
		padding: 5px;
	}
</style>
