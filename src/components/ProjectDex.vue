<template lang="">
    <div id="ProjectDex">
      <img src="../assets/ProjectDexLogo.png" @click="dex = 1">
      <p>Project Dex</p>
      <div v-if="this.dex != 0">
        <img  class="modal" src="../assets/modal3.png" @click="dex--">
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
</style>