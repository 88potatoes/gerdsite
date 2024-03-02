<script setup>
import GardenComponent from './components/GardenComponent.vue'
import SnailHeader from './components/SnailHeader.vue'
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
}
</style>
