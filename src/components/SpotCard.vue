<template>
  <div class="card">
    <h3>{{ nameSpot }}</h3>
    <p>{{ adressSpot }}</p>
    <p>{{ cpSpot }}</p>
    <p>{{ villeSpot }}</p>

    <img class="picture" :src="'/public/image/' + picture" />
  </div>
</template>

<script setup>
defineProps(["nameSpot", "adressSpot", "cpSpot", "villeSpot", "picture"]);
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Playwrite+CU:wght@100&display=swap");

.card {
  font-family: "Playwrite CU", sans-serif;
  color: black;
  text-align: center;
  border: solid;
  border-radius: 5%;
}
.picture {
  width: 50%;
}
</style>
