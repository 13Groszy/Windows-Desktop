<template>
  <div id="Contact">
    <img src="../assets/mailbox.jpg" @click="contact = 1" />
    <p>Contact Me</p>
    <div v-if="this.contact != 0">
      <img class="modal" src="../assets/modal2.jpeg" @click="contact--" />
    </div>
  </div>
</template>
<script>
export default {
  name: "Contact",
  components: {},
  data: function () {
    return {
      contact: 0,
    };
  },
};
</script>
<style scoped>
img {
  height: 70px;
  width: 70px;
  bottom: 80%;
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