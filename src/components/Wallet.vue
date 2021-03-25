<template lang="">
    <div id="wallet">
      <div @click="$emit('closeWallet')">
        <img class="modal" src="../assets/modal.png">
      <p></p>
      </div>
    </div>
</template>
<script>
export default {
  name: "wallet",
  components: {},
  data: function () {
    return {
      btc: 0,
    };
  },
};
</script>

<style scoped>
img {
  height: 70px;
  width: 70px;
  bottom: 40%;
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
  left: 30px;
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
</style>