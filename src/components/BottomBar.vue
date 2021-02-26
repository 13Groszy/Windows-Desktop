<template lang="">
<div id="BottomBar">
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
  right: 0;
  bottom:0px;
  position: bottom;
  background-color: black;
  width: 100%;
  margin-top: 12px;
  padding: 0;
  border-top: 1px solid black;
}
input {
  position: absolute;
  margin-left: 40px;
  height: 28px;
  width: 250px;
  border: 1px solid black;
}
img {
  position: absolute;
  width: 30px;
  height: 30px;
  margin-top: 2px;
  margin-left: 4px;
}
</style>