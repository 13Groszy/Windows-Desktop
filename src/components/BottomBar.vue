<template lang="">
<div id="BottomBar">
  <img src="../assets/winlogo.png" @click="bar = 1" >
  <form action="https://www.google.com/search"  method="get"  target="_blank">
    <input  name="q" placeholder="Search in google" type="text">
  </form>
  <div class="container" v-if="this.bar != 0">
    <div class="LeftBar"></div>
    <div class="Menu">
      <div class="Contact MenuBar TopBar">Contact</div>
      <div class="ProjectDex MenuBar">Project Dex</div>
      <div class="Skills MenuBar" @click="skill = 1">Skills</div>
      <div class="AboutMe MenuBar">About me</div>
    </div>
    <img class="Refresh" src="../assets/turnoff.png" @click="bar = 0" />
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
  height: 35px;
  position: fixed;
  right: 0;
  bottom: 0px;
  position: bottom;
  background-color: black;
  width: 100%;
  margin-top: 12px;
  padding: 0;
  border-top: 1px solid black;
}
input {
  position: absolute;
  margin-left: 40px;
  height: 28px;
  width: 250px;
  border: 1px solid black;
}
img {
  position: absolute;
  width: 30px;
  height: 30px;
  margin-top: 2px;
  margin-left: 4px;
}
.Menu {
  width: 253px;
  height: 300px;
  position: relative;
  background-color: grey;
  bottom: 300px;
  left: 42px;
  border-top-right-radius: 10px;
}
.TopBar:hover {
  border-top-right-radius: 10px;
}
.MenuBar {
  height: 75px;
  border-bottom: 1px solid black;
}
.MenuBar:last-child {
  border-bottom: 0;
}
.MenuBar:hover {
  opacity: 0.8;
  background-color: lightgray;
}
.Refresh {
  position: absolute;
  bottom: 120%;
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
  width: 41px;
  height: 200px;
  bottom: 35px;
  background-color: grey;
  height: 300px;
  border-right: 1px solid black;
}
</style>