<script lang="ts">
	import SourceButton from '$lib/components/SourceButton.svelte';
	import { IonPage } from 'ionic-svelte';

	export let toggle = false;
	const toggleSkeleton = () => {
		toggle = !toggle;
	};
</script>

<svelte:head>
	<title>Ionic Companion - Skeleton</title>
</svelte:head>

<IonPage>
	<ion-header translucent={true}>
		<ion-toolbar>
			<ion-buttons slot="start">
				<ion-menu-button />
			</ion-buttons>
			<ion-buttons slot="end">
				<SourceButton name="Skeleton" />
			</ion-buttons>
			<ion-title>Skeleton Text</ion-title>
			<ion-buttons slot="primary">
				<ion-button on:click={toggleSkeleton}>Toggle</ion-button>
			</ion-buttons>
		</ion-toolbar>
	</ion-header>

	<ion-content>
		<ion-list class:show={toggle} class:hide={!toggle}>
			<ion-list-header>Albums</ion-list-header>
			<ion-item>
				<ion-thumbnail slot="start">
					<img alt="img" src="../assets/img/ionic/thebeatles.jpeg" />
				</ion-thumbnail>
				<ion-label>
					<h3>Abbey Road</h3>
					<p>The Beatles</p>
					<p>1969</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="start">
					<img alt="img" src="../assets/img/ionic/pinkfloyd.jpeg" />
				</ion-thumbnail>
				<ion-label>
					<h3>The Dark Side of the Moon</h3>
					<p>Pink Floyd</p>
					<p>1973</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="start">
					<img alt="img" src="../assets/img/ionic/boniver.jpeg" />
				</ion-thumbnail>
				<ion-label>
					<h3>For Emma, Forever Ago</h3>
					<p>Bon Iver</p>
					<p>2008</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="start">
					<img alt="img" src="../assets/img/ionic/ironwine.jpeg" />
				</ion-thumbnail>
				<ion-label>
					<h3>Beast Epic</h3>
					<p>Iron & Wine</p>
					<p>2017</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="start">
					<img alt="img" src="../assets/img/ionic/porterrobinson.jpeg" />
				</ion-thumbnail>
				<ion-label>
					<h3>Worlds</h3>
					<p>Porter Robinson</p>
					<p>2014</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="start">
					<img alt="img" src="../assets/img/ionic/childishgambino.jpeg" />
				</ion-thumbnail>
				<ion-label>
					<h3>Worlds</h3>
					<p>Awaken, My Love!</p>
					<p>2016</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="start">
					<img alt="img" src="../assets/img/ionic/chancetherapper.jpeg" />
				</ion-thumbnail>
				<ion-label>
					<h3>Coloring Book</h3>
					<p>Chance the Rapper</p>
					<p>2016</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="start">
					<img alt="img" src="../assets/img/ionic/kimbra.jpeg" />
				</ion-thumbnail>
				<ion-label>
					<h3>Primal Heart</h3>
					<p>Kimbra</p>
					<p>2018</p>
				</ion-label>
			</ion-item>
		</ion-list>
		<ion-list class:show={!toggle} class:hide={toggle}>
			<ion-list-header>
				<ion-skeleton-text animated style="width: 80px" />
			</ion-list-header>
			<ion-item>
				<ion-thumbnail slot="start">
					<ion-skeleton-text />
				</ion-thumbnail>
				<ion-label>
					<h3>
						<ion-skeleton-text animated style="width: 80%" />
					</h3>
					<p>
						<ion-skeleton-text animated style="width: 60%" />
					</p>
					<p>
						<ion-skeleton-text animated style="width: 30%" />
					</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="start">
					<ion-skeleton-text />
				</ion-thumbnail>
				<ion-label>
					<h3>
						<ion-skeleton-text animated style="width: 80%" />
					</h3>
					<p>
						<ion-skeleton-text animated style="width: 60%" />
					</p>
					<p>
						<ion-skeleton-text animated style="width: 30%" />
					</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="start">
					<ion-skeleton-text />
				</ion-thumbnail>
				<ion-label>
					<h3>
						<ion-skeleton-text animated style="width: 80%" />
					</h3>
					<p>
						<ion-skeleton-text animated style="width: 60%" />
					</p>
					<p>
						<ion-skeleton-text animated style="width: 30%" />
					</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="start">
					<ion-skeleton-text />
				</ion-thumbnail>
				<ion-label>
					<h3>
						<ion-skeleton-text animated style="width: 80%" />
					</h3>
					<p>
						<ion-skeleton-text animated style="width: 60%" />
					</p>
					<p>
						<ion-skeleton-text animated style="width: 30%" />
					</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="start">
					<ion-skeleton-text />
				</ion-thumbnail>
				<ion-label>
					<h3>
						<ion-skeleton-text animated style="width: 80%" />
					</h3>
					<p>
						<ion-skeleton-text animated style="width: 60%" />
					</p>
					<p>
						<ion-skeleton-text animated style="width: 30%" />
					</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="start">
					<ion-skeleton-text />
				</ion-thumbnail>
				<ion-label>
					<h3>
						<ion-skeleton-text animated style="width: 80%" />
					</h3>
					<p>
						<ion-skeleton-text animated style="width: 60%" />
					</p>
					<p>
						<ion-skeleton-text animated style="width: 30%" />
					</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="start">
					<ion-skeleton-text />
				</ion-thumbnail>
				<ion-label>
					<h3>
						<ion-skeleton-text animated style="width: 80%" />
					</h3>
					<p>
						<ion-skeleton-text animated style="width: 60%" />
					</p>
					<p>
						<ion-skeleton-text animated style="width: 30%" />
					</p>
				</ion-label>
			</ion-item>
			<ion-item>
				<ion-thumbnail slot="start">
					<ion-skeleton-text />
				</ion-thumbnail>
				<ion-label>
					<h3>
						<ion-skeleton-text animated style="width: 80%" />
					</h3>
					<p>
						<ion-skeleton-text animated style="width: 60%" />
					</p>
					<p>
						<ion-skeleton-text animated style="width: 30%" />
					</p>
				</ion-label>
			</ion-item>
		</ion-list>
	</ion-content>
</IonPage>

<style>
	.show {
		display: block;
	}

	.hide {
		display: none;
	}
</style>
