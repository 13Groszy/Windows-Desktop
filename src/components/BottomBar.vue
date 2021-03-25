<template lang="">
<div id="BottomBar">
  <img src="../assets/winlogo.png" @click="bar = 1" >
  <form action="https://www.google.com/search"  method="get"  target="_blank">
    <input  name="q" placeholder="Search in Google" type="text">
  </form>
  <div class="container" v-if="this.bar != 0">
    <div class="LeftBar"></div>
    <div class="Menu">
      <ul  class="MenuBar">
        <li><img src="../assets/Mini/ContactMe.png"><span>Contact</span></li>
        <li><img src="../assets/Mini/Documents.png"><span>Project Dex</span></li>
        <li><img src="../assets/Mini/Skills.png"><span>Skills</span></li>
        <li><img src="../assets/Mini/AboutMe.png"><span>About me</span></li>
        <li><img src="../assets/Mini/github.png"><span>GitHub</span></li>
        <li @click="$emit('openWallet')"><img src="../assets/Mini/FunnyCats.png"><span>APICOINS</span></li>
        <li><img src="../assets/Mini/PokeXGames.png"><span>PokeXGames</span></li>
      </ul>
    </div>
    <div class="Off" @click="bar = 0" >
    <img class="Refresh" src="../assets/turnoff.png" />
    </div>
    <img class="Burger" src="../assets/burger.png" />
  </div>

</div>

</template>
<script>
export default {
  name: "BottomBar",
  components: {},
  data: function () {
    return {
      bar: 0,
    };
  },
};
</script>
<style scoped>
#BottomBar {
  z-index: 15;
  height: 35px;
  position: fixed;
  right: 0;
  bottom: 0;
  position: bottom;
  background-color: rgba(32, 32, 32, 0.7);
  width: 100%;
  margin-top: 12px;
  padding: 0;
  color: grey;
}

input {
  position: absolute;
  margin-left: 40px;
  height: 32px;
  width: 200px;
  border: 1px solid #000;
}

img {
  position: absolute;
  width: 30px;
  height: 30px;
  margin-top: 2px;
  margin-left: 4px;
}

.Menu {
  width: 245px;
  height: 300px;
  position: relative;
  background-color: #202020;
  bottom: 312px;
}
.MenuBar {
  width: 205px;
  height: 400px;
}

li:hover {
  opacity: 0.8px;
  background-color: rgb(54, 54, 54);
  color: rgb(255, 255, 255);
}

.Refresh {
  position: absolute;
  bottom: 80%;
  z-index: 2;
  width: 20px;
  height: 20px;
  left: 5px;
}

.Burger {
  position: absolute;
  bottom: 880%;
  left: 5px;
  z-index: 2;
  width: 20px;
  height: 20px;
}

.LeftBar {
  position: absolute;
  z-index: 1;
  width: 42px;
  bottom: 35px;
  background-color: #202020;
  height: 300px;
}

.Off {
  background-color: transparent;
  position: absolute;
  height: 50px;
  width: 50px;
  z-index: 3;
  bottom: 1px;
}
ul {
  list-style-type: none;
}
li {
  height: 38px;
  padding-top: 5px;
  padding-left: 50px;
  font-size: 15px;
}
li img {
  position: absolute;
  left: 45px;
  width: 30px;
  height: 30px;
}
span {
  position: relative;
  top: 9px;
}
</style>