<script lang="ts">
	import { techs } from '../services/techs.js';

	export let techName;
	let tech = {
		title: 'Python',
		icon: 'python',
		description: 'A clear and powerful object-oriented programming language!',
		color: '#3575AC'
	};
	//	tech = techs.find((tech) => tech.title === 'Tux');
	console.log('techs', techs, tech, techName);
</script>

<svelte:head>
	<title>Ionic Companion - AltDetail</title>
</svelte:head>

<ion-header translucent={true}>
	<ion-toolbar>
		<ion-buttons slot="start">
			<ion-back-button text="Back off!" default-href="/" color="danger" />
		</ion-buttons>
		<ion-title>{tech.title}</ion-title>
	</ion-toolbar>
</ion-header>
<ion-content fullscreen class="ion-padding">
	<ion-icon name={'logo-' + tech.icon} style="color: {tech.color}" size="large" />
	<p>{tech.description}</p>
</ion-content>
