<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Contador Interactivo</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content class="ion-padding" :fullscreen="true">
      <div class="contador-container">
        <div class="contador-valor">
          {{ contador }}
        </div>
        <div class="contador-botones">
          <ion-button
            color="danger"
            shape="round"
            size="large"
            class="ion-activatable ripple-parent"
            @click="decrementar"
          >
            -
            <ion-ripple-effect></ion-ripple-effect>
          </ion-button>

          <ion-button
            color="success"
            shape="round"
            size="large"
            class="ion-activatable ripple-parent"
            @click="incrementar"
          >
            +
            <ion-ripple-effect></ion-ripple-effect>
          </ion-button>
        </div>
      </div>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonButton, IonRippleEffect } from '@ionic/vue';

const contador = ref(0);

function incrementar() {
  contador.value++;
}

function decrementar() {
  contador.value--;
}
</script>

<style scoped>
.contador-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100%;
  gap: 30px;
}

.contador-valor {
  font-size: 3rem;
  font-weight: bold;
  color: #ffffff;
  background: rgba(0, 0, 0, 0.4);
  padding: 20px 50px;
  border-radius: 20px;
  backdrop-filter: blur(10px);
  text-align: center;
  min-width: 120px;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
}

.contador-botones {
  display: flex;
  gap: 20px;
}

ion-button {
  --box-shadow: 0 4px 12px rgba(0,0,0,0.2);
  --transition: all 0.3s ease;
}

ion-button:hover {
  transform: translateY(-2px);
}
</style>
