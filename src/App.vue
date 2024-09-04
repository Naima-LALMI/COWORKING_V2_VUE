<template>
<Header />
<SpotCard v-for="spot in spots" :key="spot.id" :nameSpot="spot.nom" :adressSpot="spot.adresse" :cpSpot="spot.cp" :villeSpot="spot.ville" :picture="spot.image" :url="spot.lien"/>


</template>

<script setup>
import {ref} from 'vue'
import Header from "@/components/Header.vue";
import SpotCard from "./components/SpotCard.vue";
const spots = ref([
  { id: 1, nom: 'Husy', adresse: '3 rue des Marins', cp: '75010', ville:'Paris', image :'coworking2.jpg', lien:'https://www.hubsy.fr/'},
  { id: 2, nom: 'Café Code',adresse: '15 rue des Lisses', cp: '75015', ville:'Paris',image :'coworking3.jpg'},
  { id: 3, nom: 'Why Work in Paris',adresse: '115 avenues des Sapins', cp: '75001', ville:'Paris' ,image :'coworking4.jpg'}
])



</script>
<Header />
<style scoped>

</style>
