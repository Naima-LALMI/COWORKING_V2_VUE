<!--MAP.VUE EST LE COMPOSANT ENFANT -->
<template>
  <div id="map" style="height: 500px"></div>

  <!--Ajouter des marqueurs à partir des données de spots-->
</template>

<script setup>
import { onMounted } from "vue";
import L from "leaflet";

// Recevoir la prop "spots" comme un tableau de données
const {spots} =  defineProps(["spots"])

onMounted(() => {
  // Initialiser la carte et définir les coordonnées initiales
  const map = L.map("map").setView([48.8566, 2.3522], 13); // Latitude et longitude de Paris

  // Ajouter une couche de tuiles (carte de base)
  L.tileLayer("https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png", {
    attribution: "© OpenStreetMap contributors",
  }).addTo(map);

  for (let i = 0 ; i < spots.length ; i++){
    let spot = spots[i];
    console.log(spot)
    let latitude = spot.coordonnees.lat
    console.log(latitude)
    let longitude = spot.coordonnees.lon
    console.log(longitude)
  

  // Ajouter des marqueurs pour chaque spot après l'initialisation de la carte
  L.marker([latitude, longitude])
    .addTo(map)
    .bindPopup("A pretty CSS popup.<br> Easily customizable.")
    .openPopup();
  }
});
</script>

<style>
#map {
  height: 100%;
  width: 100%;
}
</style>
