<script setup>
import { ref } from 'vue'
import PlantComponent from './PlantComponent.vue'
import plant1 from '../plants/plant1.webp'
import plant2 from '../plants/plant2.png'
import plant3 from '../plants/plant3.webp'
import plant4 from '../plants/plant4.webp'
import plant5 from '../plants/plant5.webp'

const added = ref(false)
const turnAdded = () => {
  added.value = true
  console.log('LOG')
}
</script>

<template>
  <div class="title">
    <h1>🪴 The Wildflower Way 🪴</h1>
  </div>
  <div class="garden">
    <PlantComponent name="BONZAI" colour="#7F9C72" :imgSrc="plant1" />
    <PlantComponent name="MY BABY ❤️" colour="#A7E45A" :imgSrc="plant2" />
    <PlantComponent name="POOKIE" colour="#AFF0B5" :imgSrc="plant3" />
    <PlantComponent name="🌵" colour="#8EC58A" :imgSrc="plant4" />
    <PlantComponent name="Mans" colour="#84CCBB" :imgSrc="plant5" />
    <PlantComponent name="007" colour="#D7E0D5" :imgSrc="plant1" v-if="added" />
    <div @click="turnAdded" class="addNew">
      <div><h1>+</h1></div>
      <div><strong>Add new</strong></div>
    </div>
  </div>
</template>

<style>
.garden {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(4, 1fr);
  width: 85%;
  height: calc(100vh - 300px);
  gap: 30px;
  padding-top: 30px;
  position: relative;
}

.addNew {
  background-color: rgb(227, 227, 227);
  width: 120px;
  height: 120px;
  border-radius: 20px;
  padding: 15px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.addNew:hover {
  cursor: pointer;
}

.title {
  padding-top: 30px;
}
</style>
