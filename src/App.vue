<!--APP.VUE EST LE COMPOSANT PARENT -->

<template>
  <Header />
  <div class="mainContainer">
    <div class="spotDiv">
      <SpotCard
        v-for="(spot, index) in spots"
        :key="spot.id"
        :nameSpot="spot.nom"
        :adressSpot="spot.adresse"
        :cpSpot="spot.cp"
        :villeSpot="spot.ville"
        :picture="spot.img"
        :url="spot.web"
      />
    </div>

    <!-- Passer le tableau des spots à la carte -->
    <div class="mapDiv"><Map :spots="spots" /></div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Map from "./components/Map.vue";
import Header from "@/components/Header.vue";
import SpotCard from "./components/SpotCard.vue";


const spots = ref([]);
const img = ref([]);

async function afficherCoworking() {
  const reponse = await fetch(
    "https://public.opendatasoft.com/api/explore/v2.1/catalog/datasets/coworking-france/records?limit=4&refine=ville%3A%22Paris%22"
  );
  const coworkings = await reponse.json();

  for (let i = 0; i < coworkings.results.length; i++) {
    const response1 = await fetch(
      "https://api.unsplash.com/photos/random?client_id=B8h7TfapDvNH46X6wt-u9eICKGeKoG-xL-ld6p7xmjA&query=desk"
    );
    const imageCoworkings = await response1.json();
    coworkings.results[i].img = imageCoworkings.urls.raw;
  }

  spots.value = coworkings.results;
  console.log(spots.value)

}
afficherCoworking();

</script>

<style scoped>
.mainContainer {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}
.spotDiv {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-gap: 10px;
  width: 60%;
}

.mapDiv {
  margin-top: 35px;
  width: 35%;
  height: 500px;
  margin-left: 10px;
}
</style>
