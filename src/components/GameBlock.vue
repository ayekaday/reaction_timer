<template>
  <div class="block" v-if="showBlock">Click here {{ delay }}</div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
    }, this.delay);
  },
};
</script>

<style>
.block {
  background-color: greenyellow;
  color: crimson;
  margin: 100px auto;
  width: 300px;
  height: 100px;
  padding: 20px;
}
</style>
