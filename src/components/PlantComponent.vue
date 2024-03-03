<script setup>
import PlantPopup from './PlantPopup.vue'
import { ref } from 'vue'
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

const popupShowing = ref(false)
const togglePopup = () => {
  popupShowing.value = !popupShowing.value
  console.log(popupShowing)
}

const percentage = ref('0%')
const setPercentage = (event) => {
  percentage.value = event.target.innerText
}
</script>

<template>
  <div class="plantcomponent" :style="{ 'background-color': colour }" @click="togglePopup">
    <div class="edit"><strong>…</strong></div>
    <img class="plantimage" :src="imgSrc" alt="Plant Image" width="100" height="100" />
    <div class="nametag">{{ name }}</div>
  </div>
  <PlantPopup
    :imgSrc="imgSrc"
    alt="Plant Image"
    :name="name"
    v-if="popupShowing"
    :close="togglePopup"
    :percent="percentage"
    :setPercent="setPercentage"
  />
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

.plantcomponent:hover {
  cursor: pointer;
}

.nametag {
  font-size: 400;
  position: relative;
  color: white;
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
  right: -10px;
}

.edit {
  position: absolute;
  color: white;
  background-color: rgba(0, 0, 0, 0.5);
  width: 30px;
  height: 30px;
  border-radius: 50%;
  text-align: center;
  font-size: large;
  top: 20px;
  left: 20px;
}
</style>
