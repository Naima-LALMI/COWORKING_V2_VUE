<template>
  <div class="header">
    <h1>Coworking à Paris</h1>
      <!-- <label for="name">Recherche un lieu</label> -->
      <input class="barre" type="text" id="searchInput" placeholder="Recherche ton lieu" />
      <i class="fas fa-search"></i>
  </div>
</template>

<script setup></script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playwrite+CU:wght@100&display=swap');


.header{
background-color:whitesmoke;
text-align: center;
font-family: 'Playwrite CU', sans-serif;
border-radius: 1em;

}
h1 {
  font-size: 3em;
  color: black;
}

.barre{
    border-radius: 1em;
    text-align: center; 
    margin-top: 1em;
    margin-bottom: 1em;
}

</style>
