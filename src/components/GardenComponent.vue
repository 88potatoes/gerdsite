<script setup>
import PlantComponent from "./PlantComponent.vue"
import plant1 from "../plants/plant1.webp"
import plant2 from "../plants/plant2.webp"
import plant3 from "../plants/plant3.webp"
import plant4 from "../plants/plant4.webp"
import plant5 from "../plants/plant5.webp"
</script>

<template>
    <div class="garden">

        <PlantComponent name="Plant 1" colour="#7F9C72" :imgSrc="plant1"/>
        <PlantComponent name="Plant 2" colour="#A7E45A" :imgSrc="plant2"/>
        <PlantComponent name="Plant 3" colour="#AFF0B5" :imgSrc="plant3"/>
        <PlantComponent name="Plant 4" colour="#8EC58A" :imgSrc="plant4"/>
        <PlantComponent name="Plant 5" colour="#84CCBB" :imgSrc="plant5"/>
        <PlantComponent name="Plant 6" colour="#D7E0D5" :imgSrc="plant1"/>
    </div>
</template>

<style>
.garden {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(4, 1fr);
    width: 85%;
    height: 70%;
    gap: 30px;
}
</style>
