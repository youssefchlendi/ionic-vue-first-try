<template>
	<ion-page>
		<ion-header>
			<ion-toolbar>
				<ion-title>Photo Gallery</ion-title>
			</ion-toolbar>
		</ion-header>
		<ion-content :fullscreen="true">
			<ion-header collapse="condense">
				<ion-toolbar>
					<ion-title size="large">Tab 2</ion-title>
				</ion-toolbar>
			</ion-header>
			<ion-tab-bar>
				<ion-tab-button tab="tab2" href="/tabs/tab2">
					<ion-icon :icon="images" />
					<ion-label>Photos</ion-label>
				</ion-tab-button>
			</ion-tab-bar>
				<ion-grid>
					<ion-row>
						<ion-col size="6" :key="index" v-for="(photo, index) in photos">
							<ion-img :src="photo.webviewPath"></ion-img>
						</ion-col>
					</ion-row>
				</ion-grid>
				<ion-fab vertical="bottom" horizontal="center" slot="fixed">
					<ion-fab-button @click="takePhoto()">
						<ion-icon :icon="camera"></ion-icon>
					</ion-fab-button>
				</ion-fab>
			</ion-content>
	</ion-page>
</template>

<script lang="ts">
import { usePhotoGallery } from '@/composables/usePhotoGallery';
import { defineComponent, onMounted } from 'vue';
import { images, square, triangle } from 'ionicons/icons';
import { camera, trash, close } from 'ionicons/icons';
import {
	IonPage,
	IonHeader,
	IonFab,
	IonFabButton,
	IonIcon,
	IonToolbar,
	IonTitle,
	IonContent,
	IonGrid,
	IonRow,
	IonCol,
	IonImg,
} from '@ionic/vue';
export default defineComponent({
	name: 'Tab2Page',
	components: {
		IonPage,
		IonHeader,
		IonFab,
		IonFabButton,
		IonIcon,
		IonToolbar,
		IonTitle,
		IonContent,
		IonGrid,
		IonRow,
		IonCol,
		IonImg,
	},
	setup() {
		const { takePhoto, photos, loadSaved } = usePhotoGallery();
		onMounted(loadSaved);
		return {
			photos,
			takePhoto,
			camera,
			trash,
			close,
			images,
			square,
			triangle,
		};
	},
});
</script>
