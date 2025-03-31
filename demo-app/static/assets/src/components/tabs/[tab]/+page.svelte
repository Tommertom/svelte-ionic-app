<script lang="ts">
	// SvelteKit users - please refer to https://github.com/Tommertom/ionic-svelte-tabs-howto
	// this has a newer and better way to implement tabs, using layout-system of SvelteKit router

	import IonTabsLegacy from '$lib/IonTabsLegacy.svelte';
	import Controllers from '../../Controllers/+page.svelte';
	import Music from '$lib/components/Music.svelte';
	import TabsExplain from '$lib/components/TabsExplain.svelte';

	import type { PageData } from './$types';
	export let data: PageData;

	console.log('Receiving slug data in [tab]', data);
	const tab = data.tab;
	const myTabs = [
		{
			label: 'Explain',
			icon: 'pin',
			tab: 'explain',
			component: TabsExplain
		},
		{ label: 'Controllers', icon: 'videocam', tab: 'controllers', component: Controllers },
		{ label: 'Blabla', icon: 'musicalNote', tab: 'blabla', component: Music }
	];

	console.log('Tabs', tab, myTabs);

	const logStuff = (event: { detail: { tab: any }; type: any }) => {
		console.log('>', event?.detail?.tab, event?.type);
	};
</script>

<IonTabsLegacy
	slot="bottom"
	tabs={myTabs}
	selected={tab}
	ionTabsWillChange={logStuff}
	ionNavWillLoad={logStuff}
	ionTabsDidChange={logStuff} />
