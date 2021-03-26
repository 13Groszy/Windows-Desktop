<template lang="">
    <div id="Skills">
      <img src="../assets/Skills.png" @click="skill = 1">
      <p>Skills</p>
     <div class="outerWrapper" ref="draggableContainer"  id="draggable-container" v-if="this.skill != 0">
        <div class="topBar" id="draggable-header" @mousedown="dragMouseDown">
        <img src="../assets/exit.png" @click="skill = 0" >
        <p>ProjectsIHaveDoneSoFar.exe</p>
        </div>
        <div class="exitBar"></div>
        <div class="topic">
          <p>Sed suscipit ac erat dapibus rhoncus. Nulla vitae ipsum libero. Nullam efficitur turpis ut tempor venenatis.</p>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. In at quam nibh. </p>
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
  background-color: bisque;
  background-size: cover;
  width: 500px;
  height: 400px;
  position: absolute;
  left: 120px;
  border-radius: 0 0 5px 5px;
  box-shadow: 0px 3px 10px rgba(0, 0, 0, 0.8);
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
</style>