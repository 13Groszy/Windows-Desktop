<template>
  <div id="Contact">
    <img src="../assets/mailbox.jpg" @click="skill = 1" />
    <div v-if="this.skill != 0">
      <img class="modal" src="../assets/modal2.jpeg" @click="skill--" />
    </div>
  </div>
</template>
<script>
export default {
  name: "Contact",
  components: {},
  data: function () {
    return {
      skill: 0,
    };
  },
};
</script>
<style scoped>
body {
  position: absolute;
}
img {
  height: 70px;
  width: 70px;
  bottom: 80%;
  left: 10px;
}
img:hover {
  height: 75px;
  width: 75px;
  left: 10px;
  bottom: 79.5%;
}
.modal {
  width: 50%;
  height: 50%;
  bottom: 24%;
  left: 10%;
  border: 2px solid #f0f8ff;
  border-radius: 50px;
}
.modal:hover {
  width: 51%;
  height: 51%;
  bottom: 24%;
  left: 9.5%;
}
</style>