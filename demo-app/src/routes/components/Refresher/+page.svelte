<script lang="ts">
	import { onMount } from 'svelte';
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';

	const names = [
		'Burt Bear',
		'Charlie Cheetah',
		'Donald Duck',
		'Eva Eagle',
		'Ellie Elephant',
		'Gino Giraffe',
		'Isabella Iguana',
		'Karl Kitten',
		'Lionel Lion',
		'Molly Mouse',
		'Paul Puppy',
		'Rachel Rabbit',
		'Ted Turtle'
	];

	let refresher;
	let itemList = [];

	const refreshAction = () => {
		console.log('Refresh action');
		setTimeout(() => {
			prependMessages(5, true);
			refresher.complete();
		}, 2000);
	};

	onMount(() => {
		appendMessages(5, false);
	});

	// This needs to be done in svelte-way, not javascript dom manipulation!
	const chooseRandomName = () => {
		return names[Math.floor(Math.random() * names.length)];
	};

	const createMessage = (i, unread) => {
		return {
			avatar: `https://www.gravatar.com/avatar/${i}?d=monsterid&f=y`,
			unread
		};
	};

	const appendMessages = (numMessages = 1, unread) => {
		for (let i = 0; i < numMessages; i++) {
			const newItem = createMessage(i, unread);
			itemList = [newItem, ...itemList];
		}
	};

	const prependMessages = (numMessages = 1, unread) => {
		let prependList = [];
		for (let i = 0; i < numMessages; i++) {
			const newItem = createMessage(i, unread);
			prependList = [newItem, ...prependList];
		}
		itemList = itemList.concat(prependList);
	};
</script>

<svelte:head>
	<title>Ionic Companion - Refresher</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Refresher" />
			</ion-buttons>
			<ion-title>Pull to refresh</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content>
		<ion-refresher slot="fixed" bind:this={refresher} on:ionRefresh={refreshAction}>
			<ion-refresher-content />
		</ion-refresher>

		<ion-list>
			{#each itemList as item}
				<ion-item>
					<ion-avatar slot="start">
						<img src={item.avatar} alt={item.avatar} />
					</ion-avatar>
					<ion-label class="ion-text-wrap">
						<h2>{chooseRandomName()}</h2>
						<h3>Lorem ipsum dolor sit amet, consectetur adipiscing elit</h3>
					</ion-label>
				</ion-item>
			{/each}
		</ion-list>
	</ion-content>
</IonPage>

<style>
	:root {
		--ion-safe-area-top: 20px;
		--ion-safe-area-bottom: 22px;
	}
	ion-content {
		user-select: none;
	}
</style>
