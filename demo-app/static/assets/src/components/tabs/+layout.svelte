<script lang="ts">
	import IonTabs from 'ionic-svelte/components/IonTabs.svelte';

	import { videocam, pin, musicalNote } from 'ionicons/icons';

	const myTabs = [
		{
			label: 'Explain',
			icon: pin,
			tab: 'explain'
		},
		{ label: 'Controllers', icon: videocam, tab: 'controllers' },
		{ label: 'Blabla', icon: musicalNote, tab: 'blabla' }
	];

	const logStuff = () => {};
</script>

<IonTabs slot="bottom" tabs={myTabs} ionTabsWillChange={logStuff} ionTabsDidChange={logStuff}>
	<slot />
</IonTabs>
