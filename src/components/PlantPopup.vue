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
  close: {
    type: Function
  }
})

const handleClick = (event) => {
  event.stopPropogation
}
</script>

<template>
  <dialog class="popupPage" @click="close">
    <div class="plantPopup" @click.stop="handleClick">
      <div>{{ name }}</div>
      <img :src="imgSrc" alt="Plant Image" width="300" height="300" />
      <div class="closebutton" @click="close">X</div>
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
