<template>
    <div>
          <!-- <label for="name">Recherche un lieu</label> -->
          <input class="barre" type = "text" autocomplete="off" id="searchInput" placeholder="Recherche ton lieu" v-model="texte">
          <span>{{lowercaseText }}</span>

    </div>
  </template>
  
  <script setup>
 import { ref } from "vue";
 

  defineProps(["spots"]); // Reçoit les spots depuis App.vue
  
  </script>

  <style scope>

.barre {
    border-radius: 1em;
    text-align: center; 
    margin-top: 1em;
    margin-bottom: 1em;
    width: 200px;
    height: 40px; 
    font-size: 16px;
    padding: 0.5em;
    border: 1px solid black; 
    box-sizing: border-box; 
}
span {
    display: block; /* Assure que le texte en dehors de l'input soit en bloc */
    margin-top: 10px; 
    font-style: italic; 
    font-size: 16px;
}
</style>
  