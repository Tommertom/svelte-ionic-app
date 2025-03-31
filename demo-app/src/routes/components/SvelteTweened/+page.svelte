<script lang="ts">
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';
	import { tweened } from 'svelte/motion';
	import { cubicOut } from 'svelte/easing';

	const progress = tweened(0, {
		duration: 2000,
		easing: cubicOut
	});
</script>

<svelte:head>
	<title>Ionic Companion - Svelte Tweened</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="SvelteTweened" />
			</ion-buttons>
			<ion-title>Svelte Tweened </ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen class="ion-padding">
		<p>
			Svelte tweened is part of Svelte's nifty runtime features to easily add animation to DOM
			elements.This code comes from the Svelte Tutorial on <a
				href="https://svelte.dev/tutorial/tweened"
				target="_blank"
				>https://svelte.dev/tutorial/tweened
			</a>
		</p>
		"Setting values and watching the DOM update automatically is cool. Know what's even cooler? Tweening
		those values. Svelte includes tools to help you build slick user interfaces that use animation to
		communicate changes."
		<br /><br />Click the percentages to see the transition
		<br /><br />
		<progress value={$progress} />

		<button on:click={() => progress.set(0)}> 0% </button>

		<button on:click={() => progress.set(0.25)}> 25% </button>

		<button on:click={() => progress.set(0.5)}> 50% </button>

		<button on:click={() => progress.set(0.75)}> 75% </button>

		<button on:click={() => progress.set(1)}> 100% </button>
	</ion-content>
</IonPage>

<style>
	progress {
		display: block;
		width: 100%;
	}
</style>
