<script lang="ts">
	import { menu, code } from 'ionicons/icons';
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { menuController } from 'ionic-svelte';
	import { IonPage } from 'ionic-svelte';
	import { register } from 'swiper/element/bundle';

	let menuIconClicked = false;

	const flipMenuOnOff = () => {
		setTimeout(() => {
			menuController.open('mainmenu');
			if (!menuIconClicked) {
				setTimeout(() => {
					menuController.close('mainmenu');
				}, 2000);
			}
		}, 2000);
	};

	const flipMenuOn = () => {
		menuIconClicked = true;
		menuController.open('mainmenu');
	};

	register();
</script>

<svelte:head>
	<title>Ionic Companion - Slides</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Slides" />
			</ion-buttons>
			<ion-title>Slides</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen class="ion-padding" scroll-y={false}>
		<swiper-container pager={true} on:reachend={flipMenuOnOff}>
			<swiper-slide>
				<img src="/logo.svg" alt="pict" />
				<h2>Welcome!</h2>

				<b> Ionic UI App</b> is a demo of the ionic framework made with Svelte<br />
				<br /><br />

				Easy start your own Ionic SvelteKit app?
				<pre>npm create ionic-svelte-app@latest </pre>

				<br />
				<br />
			</swiper-slide>
			<swiper-slide>
				<img src="../assets/img/slides/svelte.png" alt="pict" width="50%" />
				<h2>Handy tool!</h2>
				View the source code of the element you are viewing - copy/paste code, and directly link to the
				API docs!<br />
				Also in Angular, Vue, React, VanillaJS and Stencil
			</swiper-slide>
			<swiper-slide>Slide 3</swiper-slide>
		</swiper-container>
	</ion-content>
</IonPage>

<style>
	:root {
		--ion-safe-area-top: 20px;
		--ion-safe-area-bottom: 22px;
	}

	pre {
		font-size: 80%;
	}

	swiper-container {
		--swiper-pagination-bullet-inactive-color: var(--ion-color-step-200, #cccccc);
		--swiper-pagination-color: var(--ion-color-primary, #3880ff);
		--swiper-pagination-progressbar-bg-color: rgba(var(--ion-text-color-rgb, 0, 0, 0), 0.25);
		--swiper-scrollbar-bg-color: rgba(var(--ion-text-color-rgb, 0, 0, 0), 0.1);
		--swiper-scrollbar-drag-bg-color: rgba(var(--ion-text-color-rgb, 0, 0, 0), 0.5);
	}

	swiper-slide {
		display: flex;
		position: relative;
		flex-direction: column;

		flex-shrink: 0;
		align-items: center;
		justify-content: center;

		width: 100%;
		height: 100%;

		font-size: 18px;

		text-align: center;
		box-sizing: border-box;
	}

	swiper-slide img {
		width: auto;
		max-width: 40%;
		height: auto;
		max-height: 40%;
	}
</style>
