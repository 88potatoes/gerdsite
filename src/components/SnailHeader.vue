<template>
  <header>
    <img src="@/GerdaLogo.png" alt="Header Image" class="header-image" />
    <div class="header-title">
      <h1 style="font-family:'Aboreto'">GERDA</h1>

    </div>
    <div class="rectangle">
      <span class="bold-text" style="font-family:'Aboreto'">Hello Alex🌱</span>
    </div>
    <div class="hamburger-menu">
      <span></span>
      <span></span>
      <span></span>
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

.rectangle {
  position: absolute;
  top: 25%;
  right: 8%; 
  width: 200px; 
  height: 50px; 
  background: linear-gradient(to right, #b1ca9f, #b1ca9f, #7faf5d); 
  border: 1px solid #F0F0F0;
  border-radius: 38px; 
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'Nanum Myeongjo', serif;
  font-weight: bold;
  font-size: 20px;
}

.hamburger-menu {
  position: absolute;
  top: 40%;
  right: 3%;
  display: block;
  width: 40px; 
  height: 60px; 
  cursor: pointer;
}

.hamburger-menu span {
  display: block;
  height: 5px; 
  margin-bottom: 5px; 
  background-color: white; 
  border-radius: 3px; 
  transition: all 0.3s ease-in-out;
}

.hamburger-menu span:last-child {
  margin-bottom: 0; /* Removes the margin from the last line */
}
</style>
