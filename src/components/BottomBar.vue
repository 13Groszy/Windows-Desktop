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
        <li><img src="">Contact Me </li>
        <li><img src="">Project Dex</li>
        <li><img src="">Skills</li>
        <li><img src="">About me</li>
        <li><img src="">GitHub</li>
        <li><img src="">FunnyCats</li>
        <li><img src="">PokeXGames</li>
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
  border-top: 1px solid #000;
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
  width: 246px;
  height: 300px;
  position: relative;
  background-color: #202020;
  bottom: 312px;
}
.MenuBar {
  width: 204px;
  height: 400px;
}

.MenuBar li:hover {
  opacity: 0.8px;
  background-color: lightgray;
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
  height: 31px;
  padding-top: 12px;
  padding-left: 50px;
  font-size: 15px;
}
</style>