<template>
  <Header />
  <SpotCard
    v-for="spot in spots"
    :key="spot.id"
    :nameSpot="spot.nom"
    :adressSpot="spot.adresse"
    :cpSpot="spot.cp"
    :villeSpot="spot.ville"
    :picture="spot.image"
    :url="spot.web"
  />
</template>

<script setup>
import { ref } from "vue";
import Header from "@/components/Header.vue";
import SpotCard from "./components/SpotCard.vue";
const spots = ref([]);

async function afficherCoworking() {
  const reponse = await fetch(
    "https://public.opendatasoft.com/api/explore/v2.1/catalog/datasets/coworking-france/records?limit=15&refine=ville%3A%22Paris%22"
  );
  const coworkings = await reponse.json();
  spots.value = coworkings.results;
  console.log(coworkings.results);
}
afficherCoworking();
</script>
<Header />
<style scoped></style>
