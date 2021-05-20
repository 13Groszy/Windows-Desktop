<template>
  <div id="aboutMe">
    <div class="outerWrapper" ref="draggableContainer" id="draggable-container">
      <div class="topBar" id="draggable-header" @mousedown="dragMouseDown">
        <span>AboutMe.cv</span>
        <img
          class="exit"
          src="../assets/exit.png"
          @click="$emit('closeaboutMe')"
        />
      </div>
      <div class="container">
        <img src="../assets/aboutme.png" />
        <h1>Hello!</h1>
        <p>
          My name is Mateusz and I live in Yeovil, small town in United Kingdom.
          <br />
          After discovering many paths of working with the code I can finally
          call myself a self-taught web developer which focus mainly on front
          end. <br />
          My target in creating websites is keen on details, being original,
          thinking outside of the box as you can observe it on this website.
        </p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "aboutMe",
  components: {},
  data: function () {
    return {
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
.outerWrapper {
  z-index: 23;
  background: #b5bdc8;
  background: -moz-linear-gradient(
    45deg,
    #b5bdc8 0%,
    #828c95 36%,
    #28343b 100%
  );
  background: -webkit-linear-gradient(
    45deg,
    #b5bdc8 0%,
    #828c95 36%,
    #28343b 100%
  );
  background: linear-gradient(45deg, #b5bdc8 0%, #828c95 36%, #28343b 100%);
  filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#b5bdc8', endColorstr='#28343b',GradientType=1 );

  background-size: cover;
  width: 500px;
  height: 500px;
  position: absolute;
  left: 30%;
  top: 20%;
  border-radius: 0 0 5px 5px;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.8);
}
.container {
  display: flex;
  flex-direction: column;
  margin-top: 15%;
  justify-content: center;
}
h1 {
  width: 100%;
  margin-left: 30%;
}
p {
  margin-left: 30%;
  margin-right: 10%;
  font-size: 18px;
}

.bar {
  width: 470px;
  height: 20px;
  position: absolute;
}

.topBar {
  background: -moz-linear-gradient(
    -45deg,
    rgba(216, 224, 222, 0.8) 0%,
    rgba(216, 224, 222, 0.98) 17%,
    rgba(203, 212, 210, 1) 19%,
    rgba(78, 92, 90, 0.91) 39%,
    rgba(78, 92, 90, 0.86) 50%,
    rgba(94, 109, 106, 0.85) 52%,
    rgba(174, 191, 188, 0.9) 62%,
    rgba(47, 51, 50, 1) 81%,
    rgba(14, 14, 14, 0.93) 86%,
    rgba(14, 14, 14, 0.75) 100%
  );
  background: -webkit-linear-gradient(
    -45deg,
    rgba(216, 224, 222, 0.8) 0%,
    rgba(216, 224, 222, 0.98) 17%,
    rgba(203, 212, 210, 1) 19%,
    rgba(78, 92, 90, 0.91) 39%,
    rgba(78, 92, 90, 0.86) 50%,
    rgba(94, 109, 106, 0.85) 52%,
    rgba(174, 191, 188, 0.9) 62%,
    rgba(47, 51, 50, 1) 81%,
    rgba(14, 14, 14, 0.93) 86%,
    rgba(14, 14, 14, 0.75) 100%
  );
  background: linear-gradient(
    135deg,
    rgba(216, 224, 222, 0.8) 0%,
    rgba(216, 224, 222, 0.98) 17%,
    rgba(203, 212, 210, 1) 19%,
    rgba(78, 92, 90, 0.91) 39%,
    rgba(78, 92, 90, 0.86) 50%,
    rgba(94, 109, 106, 0.85) 52%,
    rgba(174, 191, 188, 0.9) 62%,
    rgba(47, 51, 50, 1) 81%,
    rgba(14, 14, 14, 0.93) 86%,
    rgba(14, 14, 14, 0.75) 100%
  );
  filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#ccd8e0de', endColorstr='#bf0e0e0e',GradientType=1 );

  width: 470px;
  height: 20px;
}
img {
  width: 30%;
  position: absolute;
}
.topBar img {
  height: 20px;
  width: 30px;
  position: absolute;
  top: 0;
  right: 0;
}
span {
  font-size: 14px;
  margin-left: 10px;
}

@media screen and (max-width: 767px) {
  .outerWrapper {
    min-width: 240px;
    width: 100vw;
    height: 100vh;
    left: 0;
    top: 0;
  }
  .topBar {
    width: 100%;
  }
}
</style>