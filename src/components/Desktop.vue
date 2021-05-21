<template>
  <div id="Desktop">
    <div class="dex">
      <img src="../assets/ProjectDexLogo.png" alt="ProjectDex" @click="$emit('opendex')" />
      <h1>Project Dex</h1>
    </div>
    <div class="contact">
      <img src="../assets/mailbox.png" alt="Contact Me" @click="$emit('opencontactUs')" />
      <h1>Email Me</h1>
    </div>
    <div class="skills">
      <img src="../assets/Skills.png" alt="Skills" @click="$emit('openskills')" />
      <h1>Skills</h1>
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
#Desktop {
  text-align: center;
}
img {
  position: relative;
  width: 80px;
  height: 80px;
}
h1 {
  color: #fff;
  font-weight: 700;
  font-size: 20px;
  margin-top: 0;
}
.dex {
  width: 120px;
  height: 147px;
}
.contact {
  width: 120px;
  height: 147px;
}
.skills {
  width: 120px;
  height: 147px;
}

@media screen and (max-width: 1200px) {
  img {
    width: 50px;
    height: 50px;
  }
  .dex {
    margin-top: 20px;
    margin-left: 20px;
    width: 110px;
    height: 120px;
  }
  .contact {
    margin-top: 20px;
    margin-left: 20px;
    width: 110px;
    height: 120px;
  }
  .skills {
    margin-top: 20px;
    margin-left: 20px;
    width: 110px;
    height: 120px;
  }
  @media screen and (max-width: 768px) {
img {
    width: 35px;
    height: 35px;
  }
  .dex {
    margin-top: 10px;
    margin-left: 10px;
    width: 70px;
    height: 80px;
  }
  .contact {
    margin-top: 10px;
    margin-left: 10px;
    width: 70px;
    height: 80px;
  }
  .skills {
    margin-top: 10px;
    margin-left: 10px;
    width: 70px;
    height: 80px;
  }
  h1 {
  font-weight: 500;
  font-size: 10px;
  }
}}
</style>
