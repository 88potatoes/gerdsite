<template>
  <header>
    <img src="@/GerdaLogo.png" alt="Header Image" class="header-image" />
    <div class="header-title">
      <h1 style="font-family:'EB Garamond'">GERDA</h1>

    </div>
  </header>
</template>

<style scoped>
header {
  width: 100vw;
  background: linear-gradient(to right, #b1ca9f, #b1ca9f, #7faf5d);
  margin: 0;
  padding: 0;
  text-align: center;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
  position: relative;
  height: 100px;
}

.header-title {
  font-family:'Nanum Myeongjo', serif;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  font-size: large;
  font-weight: 200;
}

.header-image {
  width: 100px;
  height: 100px;
  object-fit: cover;
  left: 10px;
  margin-left: 20px;
  position: absolute;
}
</style>
