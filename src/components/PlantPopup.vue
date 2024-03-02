<script setup>
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

const handleClick = (event) => {
  event.stopPropogation
}


const getColor = (per) => {
    return per == props.percent ? "#606060" : "white";
}
</script>

<template>
  <dialog class="popupPage" @click="close">
    <div class="plantPopup" @click.stop="handleClick">
      <div class="wateringText">
        Watering <span class="boldText">{{ name }}</span>
      </div>
      <img :src="imgSrc" alt="Plant Image" width="300" height="300" />
      <div class="closebutton" @click="close">X</div>
      <div class="levels">
        <div @click="setPercent" class="percentageButton" :style="{color: getColor('0%')}">0%</div>
        <div @click="setPercent" class="percentageButton" :style="{color: getColor('25%')}">25%</div>
        <div @click="setPercent" class="percentageButton" :style="{color: getColor('50%')}">50%</div>
        <div @click="setPercent" class="percentageButton" :style="{color: getColor('75%')}">75%</div>
        <div @click="setPercent" class="percentageButton" :style="{color: getColor('100%')}">100%</div>
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
  background-image: linear-gradient(to right, #bcbdbc, #c0c2c9);
  padding: 15px;
  border-radius: 25px;
  color: white;
  border: 1px solid #dbdcd9;
  position: absolute;
  bottom: -23px;
}

.plantPopup {
  width: 70%;
  height: 70%;
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  background-image: linear-gradient(to right, #999999, #7c7b7b);
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
