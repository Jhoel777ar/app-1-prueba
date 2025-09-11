<template>
  <ion-header>
    <ion-toolbar>
      <ion-title>Example</ion-title>
    </ion-toolbar>
  </ion-header>
  <ion-content color="light">
    <ion-list :inset="true">
      <ion-item :button="true">
        <ion-icon color="danger" slot="start" :icon="listCircle" size="large"></ion-icon>
        <ion-label>General</ion-label>
        <ion-note slot="end">6</ion-note>
      </ion-item>
      <ion-item :button="true">
        <ion-icon color="tertiary" slot="start" :icon="listCircle" size="large"></ion-icon>
        <ion-label>Shopping</ion-label>
        <ion-note slot="end">15</ion-note>
      </ion-item>
      <ion-item :button="true">
        <ion-icon color="success" slot="start" :icon="listCircle" size="large"></ion-icon>
        <ion-label>Cleaning</ion-label>
        <ion-note slot="end">3</ion-note>
      </ion-item>
      <ion-item :button="true">
        <ion-icon color="warning" slot="start" :icon="listCircle" size="large"></ion-icon>
        <ion-label>Reminders</ion-label>
        <ion-note slot="end">8</ion-note>
      </ion-item>
    </ion-list>

  </ion-content>
</template>

<script lang="ts">
  import {
    IonContent,
    IonHeader,
    IonIcon,
    IonItem,
    IonLabel,
    IonList,
    IonNote,
    IonTitle,
    IonToolbar,
  } from '@ionic/vue';
  import { defineComponent } from 'vue';
  import { chevronForward, listCircle } from 'ionicons/icons';

  export default defineComponent({
    components: {
      IonContent,
      IonHeader,
      IonIcon,
      IonItem,
      IonLabel,
      IonList,
      IonNote,
      IonTitle,
      IonToolbar,
    },
    setup() {
      return { chevronForward, listCircle };
    },
  });
</script>

<style scoped>
  .unread-indicator {
    background: var(--ion-color-primary);

    width: 10px;
    height: 10px;

    border-radius: 100%;

    position: absolute;

    inset-inline-start: 12px;
    top: 12px;
  }

  .metadata-end-wrapper {
    position: absolute;

    top: 10px;
    inset-inline-end: 10px;

    font-size: 0.8rem;

    display: flex;
    align-items: center;
  }

  ion-label strong {
    display: block;

    max-width: calc(100% - 60px);

    overflow: hidden;

    text-overflow: ellipsis;
  }

  ion-label ion-note {
    font-size: 0.9rem;
  }
</style>