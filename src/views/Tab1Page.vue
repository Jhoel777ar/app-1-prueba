<template>
  <ion-page class="bg-neutral-900 text-white">
    <ion-header translucent>
      <ion-toolbar class="bg-neutral-800">
        <ion-title class="text-xl font-bold">Bienvenido a Ark Dev System</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding" :fullscreen="true">
      <div class="flex flex-col items-center justify-center h-full space-y-6">
        <ion-input color="medium" v-model="nombre" type="text" label="Ingresa tu nombre" labelPlacement="floating"
          placeholder="Tu nombre aquí..." clear-input fill="outline" class="custom-input w-full max-w-xs"></ion-input>
        <ion-button color="medium" expand="block" class="btn-cristal max-w-xs" @click="generarSaludo">
          <ion-icon slot="start" :icon="happyIcon"></ion-icon>
          Saludar
        </ion-button>

        <ion-card v-if="saludo" class="saludo-card max-w-xs mx-auto">
          <ion-card-header>
            <ion-card-title>¡Hola!</ion-card-title>
          </ion-card-header>
          <ion-card-content>
            {{ saludo }}
          </ion-card-content>
        </ion-card>
      </div>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonInput, IonButton, IonIcon } from '@ionic/vue';
import { happyOutline } from 'ionicons/icons';

const nombre = ref('');
const saludo = ref('');
const happyIcon = happyOutline;

const mensajes = [
  '¡Qué alegría verte, {nombre}!',
  '¡Hola {nombre}, que tengas un gran día! 🌟',
  '¡Bienvenido, {nombre}! 👋'
];

function generarSaludo() {
  if (!nombre.value.trim()) {
    saludo.value = 'Por favor ingresa tu nombre 😉';
    return;
  }
  const mensajeAleatorio = mensajes[Math.floor(Math.random() * mensajes.length)];
  saludo.value = mensajeAleatorio.replace('{nombre}', nombre.value);
}
</script>
<style scoped>
.saludo-card {
  background: rgba(0, 0, 0, 0.5);
  color: #fff;
  backdrop-filter: blur(8px);
  border-radius: 12px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
  text-align: center;
}
</style>
