<template lang="">
    <div id="Skills">
      <img src="../assets/Skills.png" @click="skill = 1">
      <p>Skills</p>
     <div class="outerWrapper" ref="draggableContainer"  id="draggable-container" v-if="this.skill != 0">
        <div class="topBar" id="draggable-header" @mousedown="dragMouseDown">
        <img src="../assets/exit.png" @click="skill = 0" >
        <p>Skills.html</p>
        </div>
        <div class="exitBar"></div>
        <div class="topic">
          <h1>Skills</h1>
            <p>By writing 'skills' I understand languages or frameworks in which I feel good about or which I am learning</p>
            <hr>
          <h1>Languages</h1>
            <p>HTML, CSS and JavaScript are 'must have' to become FrontEnd Developer so I put the greatest emphasis on knowing them</p>
              <img src="../assets/Mini/HTML.png"> <img src="../assets/Mini/CSS.png"> <img src="../assets/Mini/JS.png">
              <hr>
          <h1>Frameworks</h1>
            <p>Vue.js is the only one framework which I am learning so far and my next step is get to know libraries like Vuex or Vue-Router</p>
              <img src="../assets/Mini/VueJs.png">
              <hr>
          <h1>Others</h1>
            <img src="../assets/Mini/GIT.png"><img src="../assets/Mini/MediaQuery.jpg">
          <p></p>
        </div>
      </div>
    </div>
</template>
<script>
export default {
  name: "Skills",
  components: {},
  data: function () {
    return {
      skill: 0,
      positions: {
        clientX: undefined,
        clientY: undefined,
        movementX: 0,
        movementY: 0,
      },
    };
  },
  methods: {
    dragMouseDown: function (e) {
      e.preventDefault();
      this.positions.clientX = e.clientX;
      this.positions.clientY = e.clientY;
      document.onmousemove = this.elementDrag;
      document.onmouseup = this.closeDragElement;
    },
    elementDrag: function (e) {
      e.preventDefault();
      this.positions.movementX = this.positions.clientX - e.clientX;
      this.positions.movementY = this.positions.clientY - e.clientY;
      this.positions.clientX = e.clientX;
      this.positions.clientY = e.clientY;
      this.$refs.draggableContainer.style.top =
        this.$refs.draggableContainer.offsetTop -
        this.positions.movementY +
        "px";
      this.$refs.draggableContainer.style.left =
        this.$refs.draggableContainer.offsetLeft -
        this.positions.movementX +
        "px";
    },
    closeDragElement() {
      document.onmouseup = null;
      document.onmousemove = null;
    },
  },
};
</script>

<style scoped>
* {
  z-index: 13;
}
img {
  height: 70px;
  width: 70px;
  bottom: 60%;
  left: 20px;
  position: relative;
  z-index: 14;
}
img:hover {
  opacity: 0.8;
}
p {
  color: white;
  font-weight: bold;
  font-size: 20px;
  left: 31px;
  top: -20px;
  position: relative;
}
.outerWrapper {
  background-color: rgb(80, 80, 80);
  background-size: cover;
  width: 500px;
  height: 470px;
  position: absolute;
  left: 250px;
  bottom: 150px;
  border-radius: 0 0 5px 5px;
  box-shadow: 0px 3px 10px rgba(0, 0, 0, 0.8);
}
.topBar {
  width: 470px;
  height: 350px;
  position: absolute;
  left: 450px;
  bottom: -90px;
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
}
.outerWrapper img:hover {
  opacity: 1;
}
.outerWrapper p {
  left: -440px;
  top: -246px;
  font-size: 14px;
  font-weight: 100;
  color: rgb(0, 0, 0);
}
.topic {
  text-align: center;
}
.topic p {
  width: 450px;
  top: 10px;
  left: 20px;
  font-size: 14px;
  color: rgb(179, 179, 179);
  margin: 7px;
}
h1 {
  margin: 7px;
}
.topic img {
  margin: 10px 20px 0px 20px;
  width: 30px;
  height: 30px;
  left: 0;
}
hr {
  margin: 10px 25px 0 25px;
}
</style>