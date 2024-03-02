<script setup>
import GardenComponent from './components/GardenComponent.vue'
import PlantPopup from './components/PlantPopup.vue'
import plant1 from "./plants/plant1.webp"
</script>

<template>
  <div class="main">
    <GardenComponent />
    <!-- <PlantPopup :imgSrc="plant1" name="Plant 1"/> -->
  </div>
</template>

<style>
.main {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
