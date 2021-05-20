<template lang="">
    <div id="wallet">
      <div class="outerWrapper" ref="draggableContainer"  id="draggable-container">
        <div class="topBar" id="draggable-header" @mousedown="dragMouseDown">
          <span>ApiCoins.txt</span>
          <img class="exit" src="../assets/exit.png" @click="$emit('closeWallet')">
        </div>
        <div class="coins">
          <h2>Choose coin and check info about it</h2>
          <img src="../assets/cryp/btc.png" @click="coinId = '1'">
          <img src="../assets/cryp/eth.png" @click="coinId = '2'">
          <img src="../assets/cryp/polka.png" @click="coinId = '71983'">
          <img src="../assets/cryp/ltc.png" @click="coinId = '7'">
          <img src="../assets/cryp/uni.png" @click="coinId = '72821'">
        </div>
        <button class="API" @click = "fetchAPIData">Check!</button>
        <p v-if=this.coin >{{result}}</p>
      </div>
    </div>
</template>
<script>
export default {
  name: "wallet",
  components: {},
  data: function () {
    return {
      positions: {
        clientX: undefined,
        clientY: undefined,
        movementX: 0,
        movementY: 0,
      },
      coinId: "",
      coin: "",
    };
  },
  methods: {
    fetchAPIData() {
      fetch(`https://coinranking1.p.rapidapi.com/coin/${this.coinId}`, {
        method: "GET",
        headers: {
          "x-rapidapi-key":
            "6a74bac8a4mshd570be2510616ebp18000ajsne44b784d3645",
          "x-rapidapi-host": "coinranking1.p.rapidapi.com",
        },
      })
        .then((response) => response.json())
        .then((json) => {
          this.coin = json.data.coin;
        })
        .catch((err) => {
          console.error(err);
        });
    },
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
  computed: {
    result() {
      return `The coin you chosen is ${this.coin.name} with symbol ${
        this.coin.symbol
      } and actual price ${this.coin.price.slice(0, 7)}$`;
    },
  },
};
</script>

<style scoped>
.outerWrapper {
  width: 500px;
  height: 300px;
  background-color: #f1ece5;
  position: absolute;
  left: 30%;
  top: 30%;
  border-radius: 0 0 5px 5px;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.8);
  z-index: 25;
}
.exit {
  position: absolute;
  width: 30px;
  height: 20.5px;
  border-radius: 1px 0 3px 0;
  right: 0;
  top: -0.3px;
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

  width: 100%;
  height: 20px;
}
.coins img {
  width: 10%;
  height: 50px;
  margin: auto 24px;
  border: 1px solid black;
}
h2 {
  text-align: center;
}
span {
  font-size: 14px;
  margin-left: 10px;
}
button {
  background-color: #85bb65;
  border: none;
  color: f1ece5;
  padding: 10px 20px;
  font-size: 16px;
  transition-duration: 0.4s;
  border-radius: 50px;
  border: #85bb65 2px solid;
  outline: none;
  position: absolute;
  left: 40.6%;
  top: 48%;
}

button:hover {
  background-color: #f1ece5;
  color: #85bb65;
}
p {
  font-size: 20px;
  font-weight: 700;
  width: 80%;
  margin: 10px;
  position: absolute;
  text-align: center;
  left: 10%;
  bottom: 12%;
}
img :target {
  background-color: #85bb65;
}
@media screen and (max-width: 767px) {
  .outerWrapper {
    left: 0;
    top: 0;
    width: 100vw;
    height: 100vh;
    min-width: 330px;
  }
  .coins {
    position: absolute;
    top: 20%;
    margin-left: auto;
    margin-right: auto;
  }
  .coins img {
    width: 10%;
    height: 50px;
    margin: auto 4.7%;
    border: 1px solid black;
  }
  button {
    top: 50%;
  }
  p {
    bottom: 20%;
  }
}
</style>