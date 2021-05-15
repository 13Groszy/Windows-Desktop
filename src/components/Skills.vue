<template lang="">
    <div id="Skills">
     <div class="outerWrapper" ref="draggableContainer"  id="draggable-container">
        <div class="bar" id="draggable-header" @mousedown="dragMouseDown">
          <p>Skills.html</p>
        </div>
        <div class="topBar">
          <img src="../assets/exit.png" @click="$emit('closeskills')">
        </div>
        <div class="topic">
          <h1>Skills</h1>
            <p>By writing 'skills' I understand languages or frameworks in which I feel good about or which I am learning</p>
            <hr>
          <h1>Languages</h1>
            <p>HTML, CSS and JavaScript are 'must have' to become FrontEnd Developer so I put the greatest emphasis on knowing them</p>
            <hr class="imgHr">
              <img src="../assets/Mini/HTML.png"> <img src="../assets/Mini/CSS.png"> <img src="../assets/Mini/JS.png">
              <hr>
          <h1>Frameworks</h1>
            <p>Vue.js is the only one framework which I am learning so far and my next step is get to know libraries like Vuex or Vue-Router</p>
            <hr class="imgHr">
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
p {
  position: relative;
}

.outerWrapper {
  background-color: #505050;
  background-size: cover;
  width: 500px;
  height: 470px;
  position: absolute;
  left: 30%;
  top: 20%;
  border-radius: 0 0 5px 5px;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.8);
}

.bar {
  width: 470px;
  height: 20px;
  position: absolute;
}

.topBar {
  background-color: #a2a2a1ff;
  width: 470px;
  height: 20px;
}

.outerWrapper p {
  left: 7px;
  top: -10px;
  font-size: 14px;
  font-weight: 100;
  color: #000;
}

.topic {
  text-align: center;
}

.topic p {
  width: 450px;
  top: 10px;
  left: 20px;
  font-size: 14px;
  color: #b3b3b3;
  margin: 7px;
}

h1 {
  margin: 7px;
  font-size: 24px;
}

.topic img {
  width: 30px;
  height: 30px;
  left: 0;
  margin: 10px 20px 0;
}

hr {
  margin: 10px 25px 0;
}
.topBar img {
  height: 20px;
  width: 30px;
  position: absolute;
  top: 0;
  right: 0;
}
@media screen and (max-width: 767px) {
  p {
    all: unset;
  }
  .outerWrapper {
    width: 100%;
    min-width: 300px;
    height: 100vh;
    left: 0;
    top: 0;
    margin: 0;
    padding: 0;
    overflow: hidden;
  }
  .bar {
    left: 10px;
    width: 100%;
    height: 20px;
  }

  .topBar {
    width: 100vw;
    min-width: 270px;
  }
  .topic img {
    width: 30px;
    height: 30px;
    left: 0;
    margin: 10px 20px 0;
  }

  hr {
    margin: 2vw 5vw 0;
  }
  .topic {
    width: 300px;
    margin-left: auto;
    margin-right: auto;
  }
  .imgHr {
    border: 1px solid transparent;
    height: 0px;
  }
}
</style>