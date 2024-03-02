<script setup>
import { computed } from 'vue'

defineProps({
  name: {
    type: String,
    required: true
  },
  colour: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="plantcomponent" :style="{ 'background-color': colour }">
    <div class="nametag">{{ name }}</div>
  </div>
</template>

<style scoped>
.plantcomponent {
  grid-column: auto;
  grid-row: auto;
  border-radius: 10px;
  width: 90%;
  height: 150px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: white;
}

.nametag {
    font-size: 400;
}

.nametag::before {
    content: "";
    background-color: black;
    opacity: 0.2;
    width: 100%;
    height: 100%;
}
</style>
