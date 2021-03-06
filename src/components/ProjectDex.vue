<template lang="">
    <div id="ProjectDex">
      <img src="../assets/ProjectDexLogo.png" @click="dex = 1">
      <p>Project Dex</p>
      <div class="outerWrapper" v-if="this.dex != 0">
        <div class="topBar"   draggable="true">
        <img src="../assets/exit.png" @click="dex = 0" >
        <p>ProjectsIHaveDoneSoFar.exe</p>
        </div>
        <div class="exitBar"></div>
        <div class="topic">
          <img src="../assets/portfolio.png">
          <p>My biggest project so far is this webpage and I use it as my portfolio.</p>
          <p>Other projects, mainly done with tutorials, you can find at my GitHub repo.</p>
        </div>
      </div>
    </div>
</template>
<script>
export default {
  name: "ProjectDex",
  components: {},
  data: function () {
    return {
      dex: 0,
    };
  },
};
</script>

<style scoped>
img {
  height: 70px;
  width: 70px;
  bottom: 60%;
  left: 20px;
  position: relative;
}
img:hover {
  opacity: 0.8;
}
.modal {
  width: 50%;
  height: 50%;
  bottom: 24%;
  left: 10%;
  border: 2px solid #f0f8ff;
  border-radius: 50px;
  position: fixed;
}
.modal:hover {
  width: 51%;
  height: 51%;
  bottom: 24%;
  left: 9.5%;
  opacity: 1;
}
p {
  color: white;
  font-weight: bold;
  font-size: 20px;
  left: 7px;
  top: -20px;
  position: relative;
}
#modalP {
  color: white;
  width: 40%;
  max-width: 400px;
  height: 50%;
  left: 15%;
  text-align: justify;
  position: fixed;
  top: 45%;
  font-size: 20;
}
.outerWrapper {
  background: url("../assets/ProjectDexBg.jpg");
  background-size: cover;
  width: 500px;
  height: 400px;
  position: absolute;
  left: 120px;
  border-radius: 5px;
}
.topBar {
  width: 470px;
  height: 350px;
  position: absolute;
  left: 450px;
  bottom: -159.5px;
}
.topBar img {
  width: 30px;
  height: 20.5px;
  object-position: right top;
  border-radius: 1px 2px 3px 0;
}
.exitBar {
  background-color: #a2a2a1ff;
  width: 470px;
  height: 20px;
  border-top-left-radius: 5px;
}
.topic img {
  top: 20px;
  left: 28px;
  width: 345px;
  height: 168px;
  border-radius: 5px 5px 5px 0;
}

.outerWrapper img:hover {
  opacity: 1;
}
.outerWrapper p {
  left: -440px;
  top: -246px;
  font-size: 14px;
  font-weight: 100;
  color: black;
}
.topic p {
  width: 340px;
  color: black;
  font-size: 18px;
  font-weight: bold;
  text-align: center;
  top: 40px;
  left: 148px;
}
.topic p:last-of-type {
  left: 85px;
}
</style>