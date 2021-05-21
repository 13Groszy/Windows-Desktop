<template>
  <div id="GitHub">
    <a href="http://github.com/13Groszy" target="_blank">
      <img src="../assets/GitHub.png" alt="GitHub" />
    </a>
    <h1>GitHub</h1>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
#GitHub {
  position: absolute;
  left: 17px;
}

img {
  width: 80px;
  height: 80px;
}

h1 {
  color: #fff;
  font-weight: 700;
  font-size: 20px;
  left: 7px;
  top: -12px;
  position: relative;
}
@media screen and (max-width: 1200px) {
  img {
    width: 50px;
    height: 50px;
  }
  #GitHub {
    left: 47px;
    margin-top: 20px;
  }
  h1 {
    left: -9px;
  }
}
@media screen and (max-width: 768px) {
  img {
    width: 35px;
    height: 35px;
  }
  #GitHub {
    left: 27px;
    margin-top: 10px;
  }
  h1 {
    left: 2px;
    top:-8px;
    font-weight: 500;
    font-size: 10px;
  }
}
</style>