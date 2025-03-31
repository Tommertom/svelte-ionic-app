<script lang="ts">
	import { onMount } from 'svelte';
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';

	let listElement;
	let items;

	onMount(() => {
		items = Array.from(listElement.children);
	});

	const handleInput = (event) => {
		const query = event.target.value.toLowerCase();
		requestAnimationFrame(() => {
			items.forEach((item) => {
				const shouldShow = item.textContent.toLowerCase().indexOf(query) > -1;
				console.log('Should show', item.textContent, shouldShow);
				item.style.display = shouldShow ? 'block' : 'none';
			});
		});
	};
</script>

<svelte:head>
	<title>Ionic Companion - Searchbar</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Searchbar" />
			</ion-buttons>
			<ion-title>Searchbar</ion-title>
		</ion-toolbar>
		<ion-toolbar>
			<ion-searchbar on:ionInput={handleInput} />
		</ion-toolbar>
	</ion-header>
	<ion-content fullscreen>
		<ion-list bind:this={listElement}>
			<ion-item>Amsterdam</ion-item>
			<ion-item>Bogota</ion-item>
			<ion-item>Buenos Aires</ion-item>
			<ion-item>Cairo</ion-item>
			<ion-item>Dhaka</ion-item>
			<ion-item>Edinburgh</ion-item>
			<ion-item>Geneva</ion-item>
			<ion-item>Genoa</ion-item>
			<ion-item>Glasgow</ion-item>
			<ion-item>Hanoi</ion-item>
			<ion-item>Hong Kong</ion-item>
			<ion-item>Islamabad</ion-item>
			<ion-item>Istanbul</ion-item>
			<ion-item>Jakarta</ion-item>
			<ion-item>Kiel</ion-item>
			<ion-item>Kyoto</ion-item>
			<ion-item>Le Havre</ion-item>
			<ion-item>Lebanon</ion-item>
			<ion-item>Lhasa</ion-item>
			<ion-item>Lima</ion-item>
			<ion-item>London</ion-item>
			<ion-item>Los Angeles</ion-item>
			<ion-item>Madrid</ion-item>
			<ion-item>Manila</ion-item>
			<ion-item>New York</ion-item>
			<ion-item>Olympia</ion-item>
			<ion-item>Oslo</ion-item>
			<ion-item>Panama City</ion-item>
			<ion-item>Peking</ion-item>
			<ion-item>Philadelphia</ion-item>
			<ion-item>San Francisco</ion-item>
			<ion-item>Seoul</ion-item>
			<ion-item>Taipeh</ion-item>
			<ion-item>Tel Aviv</ion-item>
			<ion-item>Tokio</ion-item>
			<ion-item>Uelzen</ion-item>
			<ion-item>Washington</ion-item>
		</ion-list>
	</ion-content>
</IonPage>
