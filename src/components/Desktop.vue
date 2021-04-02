<template>
  <div id="Desktop">
    <div class="dex">
      <img src="../assets/ProjectDexLogo.png" @click="$emit('opendex')" />
      <p>Project Dex</p>
    </div>
    <div class="contact">
      <img src="../assets/mailbox.png" @click="$emit('opencontactUs')" />
      <p>Email Me</p>
    </div>
    <div class="skills">
      <img src="../assets/Skills.png" @click="$emit('openskills')" />
      <p>Skills</p>
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
p {
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
</style>