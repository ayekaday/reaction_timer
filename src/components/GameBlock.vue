<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    Click me {{ score }}
  </div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      score: 0,
      timer: null,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay);
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.score += 50;
      }, 50);
    },
    stopTimer() {
      clearInterval(this.timer);
      console.log(this.score);
    },
  },
};
</script>

<style>
.block {
  background-color: darkgoldenrod;
  color: cyan;
  width: 300px;
  height: 200px;
  margin: 100px auto;
  padding: 20px;
}
</style>
