<template>
  <ion-page>
    <ion-header>
      <ion-toolbar color="dark">
        <ion-buttons slot="start">
            <ion-button @click="back">
                <ion-icon slot="icon-only" :icon="arrowBackOutline"></ion-icon>
            </ion-button>
        </ion-buttons>
        <ion-title>Lifecycle</ion-title>      
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">

      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Lifecycle</ion-title>
        </ion-toolbar>
      </ion-header>

      <p>{{ name }}</p>

      <ion-input label="Nama" v-model="name" label-placement="floating" fill="solid" placeholder="Masukkan Nama"></ion-input>

    </ion-content>  
  </ion-page>
</template>  


<script setup>
import { ref, onMounted, onUpdated, onUnmounted, onBeforeMount } from "vue";
import { useRouter } from "vue-router";
import { arrowBackOutline } from "ionicons/icons";

const route = useRouter()
const name = ref('')

const back = () => {
    route.back()
}

onBeforeMount(() => {
    console.log('before mounted')
})

onMounted(() => {
    console.log('mounted')
})

onUnmounted(() => {
    console.log('Unmounted')
})

onUpdated(() => {
    console.log('updated')
})

</script>

<style></style>
