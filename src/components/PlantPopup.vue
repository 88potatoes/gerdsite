<script setup>
import { ref, onUnmounted } from 'vue';
defineProps({
  name: {
    type: String,
    required: true
  },
  imgSrc: {
    type: String,
    required: true
  },
  close: {
    type: Function
  }
})

const buttonClicked = ref(false);
let resetTimeout = null; 

const toggleButton = () => {
  buttonClicked.value = !buttonClicked.value; 

  // Clear existing timeout
  if (resetTimeout) {
    clearTimeout(resetTimeout);
  }

  // Revert button state after 3 seconds (3000 milliseconds)
  resetTimeout = setTimeout(() => {
    buttonClicked.value = false;
  }, 3000); 
};

onUnmounted(() => {
  if (resetTimeout) {
    clearTimeout(resetTimeout);
  }
});

const handleClick = (event) => {
  event.stopPropagation();
};
</script>

<template>
  <dialog class="popupPage" @click="close">
    <div class="plantPopup" @click.stop="handleClick">
      <!-- Circular button -->
      <button 
        class="circularButton" 
        @click="toggleButton" 
        :style="{ backgroundColor: buttonClicked ? '#C7E7EC' : '#98d0d9' }"
      >
        <!-- Conditional Text -->
        <span v-if="!buttonClicked" class="buttonText">Nourish me!</span>
      </button>

      <div class="wateringText">
        Watering <span class="boldText">{{ name }}</span>
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
  background-image: linear-gradient(to right, #dbdcd9, #c0c2c9);
  z-index: 10;
  border-radius: 30px;
  margin: 0;
}

dialog {
  border: none;
}

.popupPage {
  width: 100%;
  height: calc(100vh - 100px);
  position: fixed;
  bottom: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(8px);
  box-shadow: -2px 2px 4px rgba(0, 0, 0, 0.1);
  margin: 0;
  padding: 0;
  z-index: 10;
  }

.wateringText {
  position: absolute;
  top: 30px;
  text-align: left;
  padding-left: 60px;
  width: 100%;
  color: white;
  font-size: 2em; 
  font-weight: normal; 
}

.boldText {
  font-weight: bold;
}

.circularButton {
  cursor: pointer;
  height: 145px; 
  width: 145px; 
  border-radius: 50%; 
  border: 0px solid #fff; 
  position: absolute;
  left: 90px; 
  top: 50%; 
  transform: translateY(-50%); 
  transition: background-color 2s ease;
}

.buttonText {
  color: white;
  font-weight: 600;
}

</style>
