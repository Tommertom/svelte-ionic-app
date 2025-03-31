<script lang="ts">
	import { pickerController } from 'ionic-svelte';

	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';

	const showPicker = async () => {
		const defaultColumnOptions = [['Dog', 'Cat', 'Bird', 'Lizard', 'Chinchilla']];
		const multiColumnOptions = [
			['Minified', 'Responsive', 'Full Stack', 'Mobile First', 'Serverless'],
			['Tomato', 'Avocado', 'Onion', 'Potato', 'Artichoke']
		];

		const numColumns = 1,
			numOptions = 5,
			columnOptions = defaultColumnOptions;

		function getColumns(numColumns, numOptions, columnOptions) {
			let columns = [];
			for (let i = 0; i < numColumns; i++) {
				columns.push({
					name: `col-${i}`,
					options: getColumnOptions(i, numOptions, columnOptions)
				});
			}

			return columns;
		}

		function getColumnOptions(columnIndex, numOptions, columnOptions) {
			let options = [];
			for (let i = 0; i < numOptions; i++) {
				options.push({
					text: columnOptions[columnIndex][i % numOptions],
					value: i
				});
			}

			return options;
		}

		const options = {
			columns: getColumns(numColumns, numOptions, columnOptions),
			buttons: [
				{
					text: 'Cancel',
					role: 'cancel'
				},
				{
					text: 'Confirm',
					handler: (value) => {
						console.log(`Got Value ${value}`);
					}
				}
			]
		};

		const picker = await pickerController.create(options);
		picker.present();
	};
</script>

<svelte:head>
	<title>Ionic Companion - Picker</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Picker" />
			</ion-buttons>
			<ion-title>Picker</ion-title>
		</ion-toolbar>
	</ion-header>

	<ion-content fullscreen class="ion-padding">
		<ion-button expand="block" on:click={showPicker}>Show Picker</ion-button>
	</ion-content>
</IonPage>
