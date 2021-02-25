<template>
  <div id="app">
    <Homepage />
    <bottom-bar />
  </div>
</template>

<script>
import BottomBar from "./components/BottomBar.vue";

import Homepage from "./components/Homepage.vue";

export default {
  name: "App",
  components: {
    Homepage,
    BottomBar,
  },
};
</script>

<style>
body {
  overflow: hidden;
  margin: 0;
  padding: 0;
  background-color: gold;
}
</style>
