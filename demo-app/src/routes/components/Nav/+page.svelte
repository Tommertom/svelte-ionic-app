<script lang="ts">
	import { IonNav } from 'ionic-svelte';
	import NavHome from '$lib/components/NavHome.svelte';
</script>

<svelte:head>
	<title>Ionic Companion - Nav</title>
</svelte:head>

<IonNav root={NavHome} />
