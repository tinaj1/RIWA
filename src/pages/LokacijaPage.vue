<template>
  <q-page class="q-pa-lg">

    <div class="text-h4 q-mb-md">
      Lokacija
    </div>

    <div class="text-body1 q-mb-lg">
      Pronađite nas na karti.
    </div>

    <div id="map"></div>

  </q-page>
</template>

<script setup>
import { onMounted } from 'vue'
import L from 'leaflet'
import 'leaflet/dist/leaflet.css'

onMounted(() => {
  const map = L.map('map').setView([45.3312, 14.4322], 13)

  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '&copy; OpenStreetMap contributors'
  }).addTo(map)

  L.marker([45.3312, 14.4322])
    .addTo(map)
    .bindPopup('Gradska knjižnica Rijeka')
    .openPopup()
})
</script>

<style scoped>
#map {
  height: 500px;
  width: 100%;
}
</style>