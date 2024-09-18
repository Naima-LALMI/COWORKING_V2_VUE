<!--SPOTCARD.VUE EST LE COMPOSANT ENFANT -->

<script setup>
defineProps([
  "nameSpot",
  "adressSpot",
  "cpSpot",
  "villeSpot",
  "picture",
  "url",
]);



</script>

<template>
  <div class="card">
    <div class="styleElement">
      <h3>{{ nameSpot }}</h3>
      <p>{{ adressSpot }}</p>
      <p>{{ cpSpot }}</p>
      <p>{{ villeSpot }}</p>
    </div>

    <a class="lienSpot" :href="'//' + url" target="_blank">Visite le lieu</a>

    <img class="picture" :src="picture" />
  </div>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Playwrite+CU:wght@100&display=swap");

template {
  display: grid;
}
.card {
  margin-top: 2em;
  font-family: "Playwrite CU", sans-serif;
  color: black;
  text-align: center;
  border: solid;
  border-radius: 5%;
}

.styleElement {
  margin-top: 1em;
  margin-bottom: 1em;
}

.lienSpot {
  background-color: whitesmoke;
  margin-top: 10em;
  border: solid;
  border-radius: 30px;
  color: black;
}
.picture {
  width: 50%;
  height: auto;
  margin: 3em;
}
</style>
