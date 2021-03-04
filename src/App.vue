<template>
  <div id="app">
    <Project-dex />
    <Skills />
    <Contact />
    <RecycleBin />
    <Bottom-Bar />
  </div>
</template>

<script>
import BottomBar from "./components/BottomBar.vue";
import Contact from "./components/Contact.vue";
import ProjectDex from "./components/ProjectDex.vue";
import Skills from "./components/Skills.vue";
import RecycleBin from "./components/RecycleBin.vue";

export default {
  name: "App",
  components: {
    BottomBar,
    Contact,
    ProjectDex,
    Skills,
    RecycleBin,
  },
  data: function () {
    return {
      bar: 0,
      contact: 0,
      skill: 0,
      dex: 0,
      aboutme: 0,
    };
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
}
img {
  position: absolute;
}
</style>
