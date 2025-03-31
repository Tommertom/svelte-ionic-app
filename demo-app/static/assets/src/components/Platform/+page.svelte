<script lang="ts">
	import SourceButton from '$lib/components/SourceButton.svelte';

	import {
		getPlatforms,
		isPlatform,
		height,
		width,
		isRTL,
		is,
		url,
		isPortrait,
		isLandscape,
		getQueryParam,
		toggleDarkTheme,
		prefersDark,
		keydown,
		resize
	} from 'ionic-svelte';
	import { IonPage } from 'ionic-svelte';

	let platforms: string[] = getPlatforms();

	const platformItems = {
		height: height(),
		width: width(),
		url: url(),
		isRTL: isRTL(),
		isPortrait: isPortrait(),
		isLandscape: isLandscape(),
		is_ios: is('ios'),
		isPlatform_ios: isPlatform('ios'),
		getQueryParam_stuff: getQueryParam('stuff'),
		prefersDark: $prefersDark
	};

	$: platformItems.prefersDark = $prefersDark;

	const platformItemKeys = Object.keys(platformItems);

	const getRandomAvatar = () => {
		const ran = Math.round(Date.now() * Math.random());
		return `https://www.gravatar.com/avatar/${ran}?d=monsterid&f=y`;
	};

	// not working  <ion-button on:click={toggleDark}>asdsads</ion-button>
	function toggleDark() {
		toggleDarkTheme(true);
	}
</script>

<svelte:head>
	<title>Ionic Companion - Platform</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Platform" />
			</ion-buttons>
			<ion-title>Platform</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen class="ion-padding">
		<h1>Your platforms</h1>
		{#each platforms as platform}
			<ion-item>
				Platform : {platform}
			</ion-item>
		{/each}

		<h1>Platform methods</h1>
		{#each platformItemKeys as platformItemKey}
			<ion-item>
				<ion-avatar slot="start">
					<img alt="avatar" src={getRandomAvatar()} />
				</ion-avatar>
				<ion-label>
					<h2>{platformItemKey}</h2>
					<p>{platformItems[platformItemKey]}</p>
				</ion-label>
			</ion-item>
		{/each}

		<ion-item>
			<ion-avatar slot="start">
				<img alt="avatar" src={getRandomAvatar()} />
			</ion-avatar>
			<ion-label>
				<h2>Want to test query parameters?</h2>
				<p>Add</p>
				<pre>&stuff=whatever</pre>
				<p>to the url and then see the result!.</p>
			</ion-label>
		</ion-item>

		<ion-item>
			<ion-avatar slot="start">
				<img alt="avatar" src={getRandomAvatar()} />
			</ion-avatar>
			<ion-label>
				<h2>Event handler: keydown</h2>
				<p>Press some keys and see result:{$keydown}</p>
			</ion-label>
		</ion-item>

		<ion-item>
			<ion-avatar slot="start">
				<img alt="avatar" src={getRandomAvatar()} />
			</ion-avatar>
			<ion-label>
				<h2>Event handler: resize</h2>
				<p>Resize the window - timestamp: {$resize}</p>
			</ion-label>
		</ion-item>

		<ion-item>
			<ion-avatar slot="start">
				<img alt="avatar" src={getRandomAvatar()} />
			</ion-avatar>
			<ion-label class="ion-text-wrap">
				<h2>
					Please check platform.ts for other methods and stuff in there. There are readable stores
					for some key events on document and window (resize, pause, resume etc).
				</h2>
			</ion-label>
		</ion-item>
	</ion-content>
</IonPage>
