<script lang="ts">
	import { createAnimation, createGesture } from '@ionic/core';
	import { onMount } from 'svelte';
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';

	let animation;
	let gesture;
	let gesture2;

	let movableSquare;
	let moveTrack;

	let swipeTrack;
	let MAX_TRANSLATE;
	let gestureType = 'Start swiping this area!';
	let currentX;
	let deltaX;
	let velocityX;

	let clientWidth;

	let initialStep = 0;
	let started = false;

	onMount(() => {
		// Gesture 1

		// Something weird here - need a timeout to get clientWidth using svelte binding - and need ? as well to avoid error
		setTimeout(() => {
			MAX_TRANSLATE = document.querySelector('.moveTrack').clientWidth - 100;

			animation = createAnimation()
				.addElement(movableSquare)
				.duration(1000)
				.fromTo('transform', 'translateX(0)', `translateX(${MAX_TRANSLATE}px)`);

			console.log('MAX', MAX_TRANSLATE, moveTrack, moveTrack?.clientWidth);
		}, 10);

		gesture = createGesture({
			el: movableSquare,
			threshold: 0,
			onMove: (ev) => onMove(ev),
			onEnd: (ev) => onEnd(ev),
			gestureName: 'my-gesture'
		});

		const onMove = (ev) => {
			if (!started) {
				animation.progressStart();
				started = true;
			}

			animation.progressStep(getStep(ev));
		};

		const onEnd = (ev) => {
			if (!started) {
				return;
			}

			gesture.enable(false);

			const step = getStep(ev);
			const shouldComplete = step > 0.5;

			animation.progressEnd(shouldComplete ? 1 : 0, step).onFinish(() => {
				gesture.enable(true);
			});

			initialStep = shouldComplete ? MAX_TRANSLATE : 0;
			started = false;
		};

		const clamp = (min, n, max) => {
			return Math.max(min, Math.min(n, max));
		};

		const getStep = (ev) => {
			const delta = initialStep + ev.deltaX;
			return clamp(0, delta / MAX_TRANSLATE, 1);
		};

		gesture.enable(true);

		// Gesture 2
		gesture2 = createGesture({
			el: swipeTrack,
			onMove: (detail) => {
				onMove2(detail);
			},
			gestureName: 'my-gesture2'
		});

		const onMove2 = (detail) => {
			gestureType = detail.type;
			currentX = detail.currentX;
			deltaX = detail.deltaX;
			velocityX = detail.velocityX;
		};

		gesture2.enable(true);
	});
</script>

<svelte:head>
	<title>Ionic Companion - Gesture</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Gesture" />
			</ion-buttons>
			<ion-title>Gesture</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen class="ion-padding">
		<ion-card>
			<div class="moveTrack" bind:this={moveTrack}>
				<div class="square" bind:this={movableSquare} />
			</div>
			<p>Drag the square along the track.</p>
		</ion-card>

		<ion-card>
			<div class="rectangle" bind:this={swipeTrack} />
			<p>Swipe to start tracking</p>
			<div>Type: {gestureType}</div>
			<div>Current X: {currentX}</div>
			<div>Delta X: {deltaX}</div>
			<div>Velocity X: {velocityX}</div>
		</ion-card>
	</ion-content>
</IonPage>

<style>
	.square {
		width: 100px;
		height: 100px;
		background: rgba(0, 0, 255, 0.5);
	}

	.moveTrack {
		width: 100%;
		max-width: 500px;
		background: rgba(0, 0, 0, 0.2);
	}

	.rectangle {
		width: 500px;
		height: 100px;
		background: rgba(0, 0, 255, 0.5);
	}
</style>
