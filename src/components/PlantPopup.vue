<script setup>
defineProps({
  name: {
    type: String,
    required: true
  },
  imgSrc: {
    type: String,
    required: true
  },
  open: {
    type: Boolean,
    required: true
  }

})

</script>

<template>
  <dialog class="popupPage">
    <div class="plantPopup">
      <div class="wateringText">
        Watering <span class="boldText">{{ plantName }}</span>
      </div>
      <img :src="imgSrc" alt="Plant Image" width="300" height="300" />
    </div>
  </dialog>
</template>

<style scoped>
.plantPopup {
  width: 70%;
  height: 70%;
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-color: rgba(192, 194, 201, 0.93);
  z-index: 10;
  border-radius: 30px;
  margin: 0;

}

dialog {
    border: none;
}

.popupPage {
  width: 100%;
  height: 100%;
  position: fixed;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background: rgba(255, 255, 255, 0.2); 
  backdrop-filter: blur(8px);
  box-shadow: -2px 2px 4px rgba(0, 0, 0, 0.1);
  margin: 0;
  padding: 0;
  }

.wateringText {
  position: absolute;
  top: 50px;
  text-align: center;
  width: 100%;
  color: white;
  font-size: 2em; /* Adjust the size as needed, 2em is just an example and roughly equivalent to h1 size */
  font-weight: normal; /* This makes the text less bold */
}

.boldText {
  font-weight: bold;
}

</style>
