<script lang="ts">
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';
</script>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Thumbnails" />
			</ion-buttons>
			<ion-title>Thumbails</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen>
		<ion-list-header>Default</ion-list-header>
		<ion-thumbnail class="ion-margin-start">
			<img alt="avatar" src="../assets/img/ionic/avatar.svg" />
		</ion-thumbnail>

		<ion-list-header>Chip Avatar</ion-list-header>
		<ion-chip class="ion-margin-start">
			<ion-thumbnail>
				<img alt="avatar" src="../assets/img/ionic/avatar.svg" />
			</ion-thumbnail>
			<ion-label>Kit Bishop</ion-label>
		</ion-chip>

		<ion-list>
			<ion-list-header>Item Avatars</ion-list-header>
			<ion-item>
				<ion-thumbnail slot="start">
					<img alt="avatar" src="../assets/img/ionic/avatar.svg" />
				</ion-thumbnail>
				<ion-label>Lorem ipsum</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="start">
					<img alt="avatar" src="../assets/img/ionic/avatar.svg" />
				</ion-thumbnail>
				<ion-label>
					<h3>Lorem ipsum</h3>
					<p>dolor sit amet</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="start">
					<img alt="avatar" src="../assets/img/ionic/avatar.svg" />
				</ion-thumbnail>
				<ion-label>
					<h3>Lorem ipsum</h3>
					<p>dolor sit amet</p>
					<p>consectetur adipiscing elit. Duis ut urna neque.</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="end">
					<img alt="avatar" src="../assets/img/ionic/avatar.svg" />
				</ion-thumbnail>
				<ion-label>Lorem ipsum</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="end">
					<img alt="avatar" src="../assets/img/ionic/avatar.svg" />
				</ion-thumbnail>
				<ion-label>
					<h3>Lorem ipsum</h3>
					<p>dolor sit amet</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="end">
					<img alt="avatar" src="../assets/img/ionic/avatar.svg" />
				</ion-thumbnail>
				<ion-label>
					<h3>Lorem ipsum</h3>
					<p>dolor sit amet</p>
					<p>consectetur adipiscing elit. Duis ut urna neque.</p>
				</ion-label>
			</ion-item>
		</ion-list>
	</ion-content>
</IonPage>
