<template>
  <ion-page>
    <!-- Encabezado -->
    <ion-header>
      <ion-toolbar>
        <ion-title>Formulario de Prueba</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content class="ion-padding">

      <ion-list>
        <ion-item>
          <ion-input label="Default input"></ion-input>
        </ion-item>

        <ion-item>
          <ion-input label="Input con placeholder" placeholder="Ingresa el nombre de tu empresa"></ion-input>
        </ion-item>

        <ion-item>
          <ion-input label="Input con valor" value="121 S Pinckney St #300"></ion-input>
        </ion-item>

        <ion-item>
          <ion-input label="Readonly input" value="Madison" :readonly="true"></ion-input>
        </ion-item>

        <ion-item>
          <ion-input label="Disabled input" value="53703" :disabled="true"></ion-input>
        </ion-item>
      </ion-list>
      <ion-button expand="block" id="present-alert">
        Da un click 😏
      </ion-button>

      <ion-alert
        trigger="present-alert"
        header="Un título corto"
        sub-header="Un subtítulo opcional"
        message="Este es un mensaje de ejemplo en IonAlert."
        :buttons="alertButtons"
      >
      </ion-alert>

    </ion-content>
  </ion-page>
</template>

<script lang="ts" setup>
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonList,
  IonItem,
  IonInput,
  IonButton,
  IonAlert
} from '@ionic/vue'

const alertButtons = ['OK']
</script>
