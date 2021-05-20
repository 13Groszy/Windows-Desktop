<template>
  <div id="app">
    <Project-dex v-if="dex" @closedex="dex = false" />
    <Contact-us v-if="contactUs" @closecontactus="contactUs = false" />
    <Skills v-if="skills" @closeskills="skills = false" />
    <Desktop
      @opencontactUs="contactUs = true"
      @opendex="dex = true"
      @openskills="skills = true"
    />
    <GitHub @openGH="GH = true" />
    <Wallet v-if="wallet" @closeWallet="wallet = false" />
    <AboutMe v-if="aboutMe" @closeaboutMe="aboutMe = false" />
    <Bottom-Bar
      @openWallet="wallet = true"
      @opencontactUs="contactUs = true"
      @openskills="skills = true"
      @opendex="dex = true"
      @openaboutMe="aboutMe = true"
      @closedex="dex = false"
      @closecontactus="contactUs = false"
      @closeskills="skills = false"
      @closeWallet="wallet = false"
      @closeaboutMe="aboutMe = false"
    />
  </div>
</template>

<script>
import BottomBar from "./components/BottomBar.vue";
import ProjectDex from "./components/ProjectDex.vue";
import Skills from "./components/Skills.vue";
import Wallet from "./components/Wallet.vue";
import ContactUs from "./components/ContactUs.vue";
import GitHub from "./components/GitHub.vue";
import Desktop from "./components/Desktop.vue";
import AboutMe from './components/AboutMe.vue';

export default {
  name: "App",
  components: {
    BottomBar,
    ProjectDex,
    Skills,
    Wallet,
    ContactUs,
    GitHub,
    Desktop,
    AboutMe,
  },
  data() {
    return {
      wallet: false,
      contactUs: false,
      skills: false,
      dex: false,
      aboutMe: false,
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
  background-color: #000;
  margin: 0;
  padding: 0;
}

p,
label {
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
@media screen and (max-width: 1200px) {
  body {
    background: url("./assets/homepageTo1200.png") no-repeat center center fixed;
    background-size: 60%;
    background-color: #000;
    background-position-x: 90%;
    background-position-y: 5%;
  }
}
</style>
