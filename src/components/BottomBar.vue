<template lang="">
    <div>
<img src="../assets/winlogo.png">
<form action="https://www.google.com/search"  method="get"  target="_blank">
<input  name="q" placeholder="Search in google" type="text">
</form>
 </div>
</template>
<script>
export default {
  name: "BottomBar",
  components: {},
};

</script>
<style scoped>
div {
  height: 35px;
  position: fixed;
  top: 94%;
  position: bottom;
  background-color: black;
  width: 100%;
  margin-top: 12px;
  padding: 0;
}
input {
  posiotion: absolute;
  margin-left: 40px;
  height: 28px;
  width: 250px;
}
img {
  position: absolute;
  width: 30px;
  height: 30px;
}
</style>