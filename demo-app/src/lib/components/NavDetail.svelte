<script lang="ts">
	import type { Tech } from '$lib/services/techs';
	import * as allIonicIcons from 'ionicons/icons';
	export let tech: Tech;

	console.log('TEC', tech);
</script>

<ion-header translucent>
	<ion-toolbar>
		<ion-buttons slot="start">
			<ion-back-button text="Back off!" default-href="/" color="danger" />
		</ion-buttons>
		<ion-title>{tech.title}</ion-title>
	</ion-toolbar>
</ion-header>
<ion-content fullscreen class="ion-padding">
	<ion-icon icon={allIonicIcons[tech.icon]} style="color: {tech.color};" size="large" />
	<p>{tech.description}</p>
</ion-content>
