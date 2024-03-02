<script setup>
defineProps({
  name: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="plantcomponent">
    <div>
      <strong>{{ name }}</strong>
    </div>
  </div>
</template>

<style scoped>
    .plantcomponent {
        border: 2px solid black;
        width: 200px;
        height: 200px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
</style>
