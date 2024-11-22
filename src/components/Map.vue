<template>
  <div style="height: 600px; width: 800px">
    <l-map ref="map" v-model:zoom="zoom" :center="[46.603354, 1.8883335]">
      <l-tile-layer
        url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"
        layer-type="base"
        name="OpenStreetMap"
      ></l-tile-layer>
      <l-marker
        v-for="spot in allspots"
        :key="spot.name"
        :lat-lng="spot.coordinates"
      >
        <l-popup>
          <h1>{{ spot.name }}</h1>
        </l-popup>
      </l-marker>
    </l-map>
  </div>
</template>

<script>
import "leaflet/dist/leaflet.css";
import { LMap, LTileLayer, LMarker, LPopup } from "@vue-leaflet/vue-leaflet";

export default {
  props: ["allspots"],
  components: {
    LMap,
    LTileLayer,
    LMarker,
    LPopup,
  },
  data() {
    return {
      zoom: 5,
    };
  },
};
</script>

<style></style>
