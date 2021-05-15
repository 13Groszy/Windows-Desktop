<template lang="">
<div id="BottomBar">
  <div class="barWrapper">
    <img src="../assets/winlogo.png" @click="bar = 1" >
    <form action="https://www.google.com/search"  method="get"  target="_blank">
      <input  name="q" placeholder="Search in Google" onfocus="this.value=''" type="text">
    </form>
  </div>
  <div class="container" v-if="this.bar != 0">
    <div class="leftBar">
      <img class="Burger" src="../assets/burger.png" />
      <div class="off" @click="bar = 0" >
        <img class="Refresh" @click="bar = 0, $emit('closedex'),$emit('closecontactus'),$emit('closeskills'),$emit('closeWallet')" src="../assets/turnoff.png" />
      </div>
    </div>
    <div class="menu">
      <ul  class="menuBar">
        <li @click="$emit('opencontactUs')"><img src="../assets/Mini/ContactMe.png"><span>Contact</span></li>
        <li @click="$emit('opendex')"><img src="../assets/Mini/Documents.png"><span>Project Dex</span></li>
        <li @click="$emit('openskills')"><img src="../assets/Mini/Skills.png"><span>Skills</span></li>
        <li><img src="../assets/Mini/AboutMe.png"><span>About me</span></li>
        <a href="http://github.com/13Groszy" target="_blank"><li><img src="../assets/Mini/github.png"><span>GitHub</span></li></a>
        <a href="https://www.pokexgames.com/#/home" target="_blank"><li><img src="../assets/Mini/PokeXGames.png"><span>PokeXGames</span></li></a>
        <li @click="$emit('openWallet')"><img src="../assets/Mini/FunnyCats.png"><span>APICOINS</span></li>
      </ul>
    </div>
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
.barWrapper {
  position: absolute;
  z-index: 20;
  height: 30px;
  width: 100%;
  bottom: 0;
  background-color: rgb(41, 39, 46);
}
.barWrapper img {
  position: relative;
  height: 70%;
  top: 15%;
  left: 8px;
}
input {
  position: relative;
  width: 150px;
  height: 25px;
  bottom: 25px;
  left: 40px;
}
.container {
  position: absolute;
  height: 400px;
  width: 300px;
  bottom: 30px;
  background-color: rgb(48, 46, 54);
}
.leftBar {
  position: absolute;
  width: 40px;
  height: 400px;
}
.leftBar img {
  position: relative;
  width: 50%;
  left: 25%;
  padding-top: 10px;
  z-index: 21;
}
.off {
  position: inherit;
  bottom: -30px;
  z-index: 22;
}
.off img {
  bottom: 30px;
}
.menu {
  position: absolute;
  width: 290px;
  height: 400px;
  bottom: 0;
  left: 10px;
  color: rgb(167, 167, 167);
}
.menuBar {
  margin: 0;
  height: 400px;
}
.menuBar img {
  width: 53px;
  height: 53px;
}
.menuBar span {
  position: relative;
  bottom: 20px;
  left: 20px;
}
li {
  list-style-type: none;
}
a {
  text-decoration: none;
  color: rgb(167, 167, 167);
}

li:hover {
  background-color: rgb(167, 167, 167);
  color: black;
}
@media screen and (max-width: 1200px) {
  .menu {
    width: 200px;
  }
  .container {
    width: 210px;
    overflow: hidden;
  }
  li {
    font-size: 10px;
  }
}
@media screen and (max-width: 767px) {
  .container {
    height: 100%;
    width: 100%;
    bottom: 30px;
    background-color: rgb(48, 46, 54);
    overflow: hidden;
  }
  .leftBar {
    width: 40px;
    height: 100%;
  }
  .leftBar img {
    width: 50%;
    left: 25%;
    padding-top: 40px;
    z-index: 21;
  }
  .menu {
    width: 100%;
    height: 100%;
    left: 20px;
  }
  .menuBar {
    margin: 0;
    height: 100%;
    position: absolute;
    bottom: -40px;
  }
  li {
    height: 13%;
    width: 100%;
  }
  .menuBar img {
    width: 20%;
    height: 80%;
    bottom: 10px;
    top: 10px;
  }

  .menuBar span {
    left: 10%;
    top: -20px;
    font-size: 15px;
  }
  li:hover {
    background-color: rgb(48, 46, 54);
  }
}
</style>