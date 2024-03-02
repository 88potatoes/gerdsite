<script setup>
import PlantComponent from "./PlantComponent.vue"
</script>

<template>
    <div class="garden">

        <PlantComponent name="Plant 1" colour="#7F9C72" />
        <PlantComponent name="Plant 2" colour="#A7E45A" />
        <PlantComponent name="Plant 3" colour="#AFF0B5" />
        <PlantComponent name="Plant 4" colour="#8EC58A" />
        <PlantComponent name="Plant 5" colour="#84CCBB" />
        <PlantComponent name="Plant 6" colour="#D7E0D5" />
    </div>
</template>

<style>
.garden {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(4, 1fr);
    width: 85%;
    gap: 30px;
    padding-top: 30px;
}
</style>
