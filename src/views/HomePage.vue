<template>
	<ion-page>
		<ion-header :translucent="true">
			<ion-toolbar>
				<ion-title>Counter App</ion-title>
			</ion-toolbar>
		</ion-header>

		<ion-content :fullscreen="true">
			<ion-header collapse="condense">
				<ion-toolbar>
					<ion-title size="large">Counter App</ion-title>
				</ion-toolbar>
			</ion-header>

			<div id="container">
				<strong>{{ counterStore.count }}</strong>
				<ion-row>
					<ion-col>
						<ion-button
							color="tertiary"
							shape="round"
							@click="counterStore.decrement()"
						>
							-</ion-button
						>
						<ion-button
							shape="round"
							@click="counterStore.increment()"
							>+</ion-button
						>
					</ion-col>
				</ion-row>
				<ion-button
					color="danger"
					@click="counterStore.$reset()"
					>Reset</ion-button
				>
			</div>
		</ion-content>
	</ion-page>
</template>

<script lang="ts">
import {
	IonContent,
	IonHeader,
	IonPage,
	IonTitle,
	IonToolbar,
	IonRow,
	IonCol,
	IonButton,
} from "@ionic/vue";
import { defineComponent } from "vue";
import { useCounterStore } from "@/stores/counter";

export default defineComponent({
	name: "HomePage",
	components: {
		IonContent,
		IonHeader,
		IonPage,
		IonTitle,
		IonToolbar,
		IonRow,
		IonCol,
		IonButton,
	},

	setup() {
		//const counterStore = useCounterStore();

		return { counterStore: useCounterStore() };
	},
});
</script>

<style scoped>
#container {
	text-align: center;

	position: absolute;
	left: 0;
	right: 0;
	top: 50%;
	transform: translateY(-50%);
}

#container strong {
	font-size: 20px;
	line-height: 26px;
}

#container p {
	font-size: 16px;
	line-height: 22px;

	color: #8c8c8c;

	margin: 0;
}

#container a {
	text-decoration: none;
}
</style>
