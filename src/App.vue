<template>
  <div id="app">
    <Contact />
    <Project-dex />
    <Skills />
    <Homepage />
    <Bottom-Bar />
  </div>
</template>

<script>
import BottomBar from "./components/BottomBar.vue";
import Homepage from "./components/Homepage.vue";
import Contact from "./components/Contact.vue";
import ProjectDex from "./components/ProjectDex.vue";
import Skills from "./components/Skills";

export default {
  name: "App",
  components: {
    Homepage,
    BottomBar,
    Contact,
    ProjectDex,
    Skills,
  },
};
</script>

<style>
body {
  overflow: hidden;
  margin: 0;
  padding: 0;
  background-color: black;
  display: grid;
  grid-template-columns: 5fr 1fr;
}
</style>
