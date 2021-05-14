<template lang="">
    <div id="ProjectDex">
      <div class="outerWrapper" ref="draggableContainer"  id="draggable-container">
        <div class="topBar" id="draggable-header" @mousedown="dragMouseDown">
          <p>ProjectsIHaveDoneSoFar.exe</p>
        </div>
        <div class="exitBar"><img src="../assets/exit.png" @click="$emit('closedex')"></div>
        <div class="topic">
          <div class="container">
            <img src="../assets/portfolio.png">
            <p>My biggest project so far is this webpage and I use it as my portfolio.</p>
            <p>Other projects, mainly done with tutorials, you can find at my GitHub repo.</p>
          </div>
        </div>
      </div>
    </div>
</template>
<script>
export default {
  name: "ProjectDex",
  data: function () {
    return {
      dex: 0,
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
  bottom: 60%;
  left: 20px;
  position: relative;
}
p {
  color: #fff;
  font-weight: 700;
  font-size: 20px;
  left: 7px;
  top: -20px;
  position: relative;
}

#modalP {
  color: #fff;
  width: 40%;
  max-width: 400px;
  height: 50%;
  left: 15%;
  text-align: justify;
  position: fixed;
  top: 45%;
  font-size: 20px;
}

.outerWrapper {
  background: url("../assets/ProjectDexBg.jpg");
  background-size: cover;
  width: 500px;
  height: 400px;
  position: absolute;
  left: 30%;
  top: 20%;
  border-radius: 0 0 5px 5px;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.8);
}

.topBar {
  width: 470px;
  height: 20px;
  position: absolute;
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

.topic img {
  top: -175px;
  left: 28px;
  width: 345px;
  height: 168px;
  border-radius: 5px 5px 5px 0;
}

.outerWrapper p {
  top: -12px;
  font-size: 14px;
  font-weight: 100;
  color: #000;
}

.topic p {
  width: 340px;
  color: #000;
  font-size: 18px;
  font-weight: 700;
  text-align: center;
  top: -180px;
  left: 148px;
}

.topic p:last-of-type {
  left: 85px;
}

.container {
  position: relative;
  top: 220px;
  height: 120px;
  background: rgba(90, 90, 90, 0.4);
}
.innerWrapper {
  height: 20px;
}
.exitBar img {
  height: 20px;
  width: 30px;
  top: 0;
  left: 100%;
}
@media screen and (max-width: 1200px) {

}
@media screen and (max-width: 767px) {

}
</style>