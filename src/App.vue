<script setup>
import GardenComponent from './components/GardenComponent.vue'
import SnailHeader from './components/SnailHeader.vue'
import PlantPopup from './components/PlantPopup.vue'
import plant1 from "./plants/plant1.webp"
</script>

<template>
  <div class="main">
    <SnailHeader />
    <GardenComponent />
  </div>
</template>

<style>
.main {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 100vh;
}
</style>
