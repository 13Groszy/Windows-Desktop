<template lang="">
    <div id="wallet">
      <div @click="$emit('closeWallet')">

      </div>
    </div>
</template>
<script>
export default {
  name: "wallet",
  components: {},
  data: function () {
    return {
      btc: 0,
    };
  },
};
</script>

<style scoped>

</style>