<script lang="ts">
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';

	import { arrowDownCircle } from 'ionicons/icons';

	let stateAccordion: HTMLIonAccordionGroupElement;

	const logAccordionValue = () => {
		console.log('stateAccordion.value', stateAccordion.value);
	};

	const closeAccordions = () => {
		stateAccordion.value = undefined;
	};
</script>

<svelte:head>
	<title>Ionic Companion - Accordion</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Accordion" />
			</ion-buttons>
			<ion-title>Accordion</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen>
		<ion-list inset={true}>
			<ion-list-header>Basic</ion-list-header>
			<ion-accordion-group>
				<ion-accordion value="colors">
					<ion-item slot="header">
						<ion-label>Colors</ion-label>
					</ion-item>

					<ion-list slot="content">
						<ion-item>
							<ion-label>Red</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Green</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Blue</ion-label>
						</ion-item>
					</ion-list>
				</ion-accordion>
				<ion-accordion value="shapes">
					<ion-item slot="header">
						<ion-label>Shapes</ion-label>
					</ion-item>

					<ion-list slot="content">
						<ion-item>
							<ion-label>Circle</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Triangle</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Square</ion-label>
						</ion-item>
					</ion-list>
				</ion-accordion>
				<ion-accordion value="numbers">
					<ion-item slot="header">
						<ion-label>Numbers</ion-label>
					</ion-item>

					<ion-list slot="content">
						<ion-item>
							<ion-label>1</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>2</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>3</ion-label>
						</ion-item>
					</ion-list>
				</ion-accordion>
			</ion-accordion-group>
		</ion-list>

		<ion-list inset={true}>
			<ion-list-header>Custom Icon</ion-list-header>
			<ion-accordion-group>
				<ion-accordion value="colors" toggle-icon={arrowDownCircle} toggle-icon-slot="start">
					<ion-item slot="header">
						<ion-label>Colors</ion-label>
					</ion-item>

					<ion-list slot="content">
						<ion-item>
							<ion-label>Red</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Green</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Blue</ion-label>
						</ion-item>
					</ion-list>
				</ion-accordion>
				<ion-accordion value="shapes" toggle-icon={arrowDownCircle} toggle-icon-slot="start">
					<ion-item slot="header">
						<ion-label>Shapes</ion-label>
					</ion-item>

					<ion-list slot="content">
						<ion-item>
							<ion-label>Circle</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Triangle</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Square</ion-label>
						</ion-item>
					</ion-list>
				</ion-accordion>
				<ion-accordion value="numbers" toggle-icon={arrowDownCircle} toggle-icon-slot="start">
					<ion-item slot="header">
						<ion-label>Numbers</ion-label>
					</ion-item>

					<ion-list slot="content">
						<ion-item>
							<ion-label>1</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>2</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>3</ion-label>
						</ion-item>
					</ion-list>
				</ion-accordion>
			</ion-accordion-group>
		</ion-list>

		<ion-list inset={true}>
			<ion-list-header>Open Accordion</ion-list-header>
			<ion-accordion-group value="colors">
				<ion-accordion value="colors">
					<ion-item slot="header">
						<ion-label>Colors</ion-label>
					</ion-item>

					<ion-list slot="content">
						<ion-item>
							<ion-label>Red</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Green</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Blue</ion-label>
						</ion-item>
					</ion-list>
				</ion-accordion>
				<ion-accordion value="shapes">
					<ion-item slot="header">
						<ion-label>Shapes</ion-label>
					</ion-item>

					<ion-list slot="content">
						<ion-item>
							<ion-label>Circle</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Triangle</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Square</ion-label>
						</ion-item>
					</ion-list>
				</ion-accordion>
				<ion-accordion value="numbers">
					<ion-item slot="header">
						<ion-label>Numbers</ion-label>
					</ion-item>

					<ion-list slot="content">
						<ion-item>
							<ion-label>1</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>2</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>3</ion-label>
						</ion-item>
					</ion-list>
				</ion-accordion>
			</ion-accordion-group>
		</ion-list>

		<ion-list inset={true}>
			<ion-list-header>Multiple Accordions</ion-list-header>
			<ion-accordion-group multiple={true} id="multiple">
				<ion-accordion value="colors">
					<ion-item slot="header">
						<ion-label>Colors</ion-label>
					</ion-item>

					<ion-list slot="content">
						<ion-item>
							<ion-label>Red</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Green</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Blue</ion-label>
						</ion-item>
					</ion-list>
				</ion-accordion>
				<ion-accordion value="shapes">
					<ion-item slot="header">
						<ion-label>Shapes</ion-label>
					</ion-item>

					<ion-list slot="content">
						<ion-item>
							<ion-label>Circle</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Triangle</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Square</ion-label>
						</ion-item>
					</ion-list>
				</ion-accordion>
				<ion-accordion value="numbers">
					<ion-item slot="header">
						<ion-label>Numbers</ion-label>
					</ion-item>

					<ion-list slot="content">
						<ion-item>
							<ion-label>1</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>2</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>3</ion-label>
						</ion-item>
					</ion-list>
				</ion-accordion>
			</ion-accordion-group>
		</ion-list>

		<ion-list inset={true}>
			<ion-list-header>Managing State</ion-list-header>
			<ion-accordion-group id="state" value="numbers" bind:this={stateAccordion}>
				<ion-accordion value="colors">
					<ion-item slot="header">
						<ion-label>Colors</ion-label>
					</ion-item>

					<ion-list slot="content">
						<ion-item>
							<ion-label>Red</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Green</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Blue</ion-label>
						</ion-item>
					</ion-list>
				</ion-accordion>
				<ion-accordion value="shapes">
					<ion-item slot="header">
						<ion-label>Shapes</ion-label>
					</ion-item>

					<ion-list slot="content">
						<ion-item>
							<ion-label>Circle</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Triangle</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>Square</ion-label>
						</ion-item>
					</ion-list>
				</ion-accordion>
				<ion-accordion value="numbers">
					<ion-item slot="header">
						<ion-label>Numbers</ion-label>
					</ion-item>

					<ion-list slot="content">
						<ion-item>
							<ion-label>1</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>2</ion-label>
						</ion-item>
						<ion-item>
							<ion-label>3</ion-label>
						</ion-item>
					</ion-list>
				</ion-accordion>
			</ion-accordion-group>
		</ion-list>

		<ion-button on:click={logAccordionValue}>Log Value of Accordion Group</ion-button>
		<ion-button on:click={closeAccordions}>Close All Accordions</ion-button>
	</ion-content>
</IonPage>

<style>
	:root {
		--ion-safe-area-top: 20px;
		--ion-safe-area-bottom: 22px;
	}

	ion-list-header {
		padding-bottom: 12px;
	}
</style>
