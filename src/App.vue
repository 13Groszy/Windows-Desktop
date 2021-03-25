<template>
  <div id="app">
    <Project-dex />
    <Contact-us />
    <Skills @click.native="searchAPI" />
    <Wallet v-if="wallet" @closeWallet="wallet = false" />
    <Bottom-Bar @openWallet="wallet = true" />
  </div>
</template>

<script>
import BottomBar from "./components/BottomBar.vue";
import ProjectDex from "./components/ProjectDex.vue";
import Skills from "./components/Skills.vue";
import Wallet from "./components/Wallet.vue";
import ContactUs from "./components/ContactUs.vue";

export default {
  name: "App",
  components: {
    BottomBar,
    ProjectDex,
    Skills,
    Wallet,
    ContactUs,
  },
  data() {
    return {
      wallet: false,
    };
  },
};
</script>

<style>
* {
  cursor: default;
}
body {
  background: url("./assets/homepage.jpg") no-repeat center center fixed;
  background-size: 90%;
  overflow: hidden;
  margin: 0;
  padding: 0;
  background-color: black;
}
p,
label {
  -webkit-user-select: none; /* Chrome all / Safari all */
  -moz-user-select: none; /* Firefox all */
  -ms-user-select: none; /* IE 10+ */
  user-select: none; /* Likely future */
}
</style>
