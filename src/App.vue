<template>
  <div id="app">
    <Contact />
    <Project-dex />
    <Skills />
    <Bottom-Bar />
  </div>
</template>

<script>
import BottomBar from "./components/BottomBar.vue";
import Contact from "./components/Contact.vue";
import ProjectDex from "./components/ProjectDex.vue";
import Skills from "./components/Skills";

export default {
  name: "App",
  components: {
    BottomBar,
    Contact,
    ProjectDex,
    Skills,
  },
};
</script>

<style>
body {
  background: url("./assets/homepage.jpg") no-repeat center center fixed;
  background-size: 90%;
  overflow: hidden;
  margin: 0;
  padding: 0;
  background-color: black;
  display: grid;
  grid-template-columns: 5fr 5fr;
}
img {
  position: absolute;
}

</style>
