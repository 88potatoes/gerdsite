<script setup>
defineProps({
  name: {
    type: String,
    required: true
  },
  colour: {
    type: String,
    required: true
  },
  imgSrc: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="plantcomponent" :style="{ 'background-color': colour }">
    <div class="nametag">{{ name }}</div>
    <img class="plantimage" :src="imgSrc" alt="Plant Image" width="100" height="100" />
  </div>
</template>

<style>
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
  bottom: 0;
  left: 0;
  position: relative;
  box-shadow: -2px 2px 4px rgba(0, 0, 0, 0.1);
}

.nametag {
  font-size: 400;
  position: relative;
  color: white;
  z-index: 5;
  background-color: rgba(0, 0, 0, 0.5);
  width: 45%;
  text-align: center;
  padding: 5px;
  border-radius: 15px;
  position: absolute;
  bottom: 15px;
  left: 20px;
  box-shadow: -1px 1px 3px rgba(0, 0, 0, 0.1);
}

.plantimage {
    position: absolute;
    right: 15px;
}
</style>
