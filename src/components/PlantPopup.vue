<script setup>
import { ref, onUnmounted } from 'vue'
const props = defineProps({
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
  },
  percent: {
    type: String
  },
  setPercent: {
    type: Function
  }
})

const buttonClicked = ref(false)
let resetTimeout = null

const toggleButton = () => {
  buttonClicked.value = !buttonClicked.value

  // Clear existing timeout
  if (resetTimeout) {
    clearTimeout(resetTimeout)
  }

  // Revert button state after 3 seconds (3000 milliseconds)
  resetTimeout = setTimeout(() => {
    buttonClicked.value = false
  }, 3000)
}

onUnmounted(() => {
  if (resetTimeout) {
    clearTimeout(resetTimeout)
  }
})

const handleClick = (event) => {
  event.stopPropogation
}

const getColor = (per) => {
  return per == props.percent ? '#606060' : 'white'
}
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
        <span v-if="!buttonClicked" class="buttonText">Water me!</span>
      </button>

      <div class="wateringText">
        <span class="boldText">{{ name }}</span>
      </div>
      <img :src="imgSrc" alt="Plant Image" width="300" height="300" />
      <div class="closebutton" @click="close">X</div>
      <!-- <div class="plant">
        <div>
            <strong>Species: </strong>Cactus
        </div>
    </div> -->
      <div class="plantinfo">
        <div>
          <strong>Species: </strong>
          <div>Cactus</div>
        </div>
        <br>
        <div>
          <strong>Last watered: </strong>
          <div>Yesterday 2:31pm</div>
        </div>
        <br>
        <div>
          <strong>Average water intake: </strong>
          <div>50ml/day</div>
        </div>
        <br>
        <div>
          <strong>Recommended water intake: </strong>
          <div>50ml/day</div>
        </div>
      </div>
      <div class="levels">
        <div @click="setPercent" class="percentageButton" :style="{ color: getColor('0%') }">
          0%
        </div>
        <div @click="setPercent" class="percentageButton" :style="{ color: getColor('25%') }">
          25%
        </div>
        <div @click="setPercent" class="percentageButton" :style="{ color: getColor('50%') }">
          50%
        </div>
        <div @click="setPercent" class="percentageButton" :style="{ color: getColor('75%') }">
          75%
        </div>
        <div @click="setPercent" class="percentageButton" :style="{ color: getColor('100%') }">
          100%
        </div>
      </div>
    </div>
  </dialog>
</template>

<style scoped>
.percentageButton:hover {
  cursor: pointer;
}
.levels {
  display: flex;
  justify-content: space-around;
  width: 350px;
  background-image: linear-gradient(to right, rgb(188, 188, 188), rgb(192, 194, 201));
  /* background-color: transparent; */
  padding: 15px;
  border-radius: 25px;
  color: white;
  border: 1px solid #dbdcd9;
  position: absolute;
  bottom: -23px;
}

.plant {
  border: 1px solid white;
  height: 65%;
  width: 200px;
  border-radius: 20px;
  padding: 10px;
  color: white;
  position: absolute;
}

.plantinfo {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: flex-start;
  border: 1px solid white;
  min-height: 50%;
  width: 200px;
  border-radius: 20px;
  padding: 10px;
  color: white;
  position: absolute;
  right: 100px;
}

.plantPopup {
  width: 70%;
  height: 70%;
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-image: linear-gradient(to right, rgba(153, 153, 153, 0.8), rgba(124, 123, 123, 0.8));
  z-index: 10;
  border-radius: 30px;
  margin: 0;
  border: 1px solid #e4e5e1;
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
  border: 1px solid #fff;
  position: absolute;
  left: 15%;
  top: 50%;
  transform: translateY(-50%);
  transition: background-color 2s ease;
}

.buttonText {
  color: white;
  font-weight: 600;
  font-size: 1.3em;
}

.closebutton {
  color: white;
  background-color: rgb(53, 50, 50);
  width: 20px;
  height: 20px;
  padding: 15px;
  text-align: center;
  border-radius: 30px;
  font-size: large;
  position: absolute;
  top: 15px;
  right: 15px;
}

.closebutton:hover {
  cursor: pointer;
}
</style>
