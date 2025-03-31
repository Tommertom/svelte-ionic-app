<script lang="ts">
	import * as allIonicIcons from 'ionicons/icons';
	import NavDetail from './NavDetail.svelte';
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { type Tech, techs } from '$lib/services/techs';
	import type { SvelteComponent } from 'svelte';
	import { navController } from 'ionic-svelte';

	// get's defined via the bind:this - too much magic imho
	export let ionNav: HTMLIonNavElement;

	const createHTMLCompFromSvelte = (
		component: new (...args: any) => SvelteComponent,
		componentProps: {}
	) => {
		const divWrapper = document.createElement('div');
		const contentID = 'id' + Date.now();
		divWrapper.id = contentID;

		let navContent = document.createElement('div');

		divWrapper.appendChild(navContent);
		document.body.appendChild(divWrapper);

		const props = {
			...componentProps,
			ionNav
		};

		const svelteComponent = new component({
			target: navContent,
			props
		});

		return divWrapper;
	};

	const showDetail = (tech: Tech) => {
		navController.push(NavDetail, { tech });
	};

	// Please note - API changes for IonNav, check https://github.com/Tommertom/ionic-svelte-nav-howto
</script>

<svelte:head>
	<title>Ionic Companion - Nav</title>
</svelte:head>

<ion-header translucent={true}>
	<ion-toolbar>
		<ion-buttons slot="start">
			<ion-menu-button />
		</ion-buttons>
		<ion-buttons slot="end">
			<SourceButton name="Nav" />
		</ion-buttons>
		<ion-title>Nav element</ion-title>
	</ion-toolbar>
</ion-header>

<ion-content fullscreen class="ion-padding">
	<ion-list>
		{#each techs as tech}
			<ion-item
				button
				on:click={() => {
					showDetail(tech);
				}}>
				<ion-icon icon={allIonicIcons[tech.icon]} style="color: {tech.color};" />
				<ion-label>
					<h3>{tech.title}</h3>
				</ion-label>
			</ion-item>
		{/each}
	</ion-list>
</ion-content>
