<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    Click Here {{ score }}
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
    },
  },
};
</script>

<style>
.block {
  background-color: darkred;
  color: floralwhite;
  width: 300px;
  height: 200px;
  margin: 100px auto;
  padding: 20px;
}
</style>
