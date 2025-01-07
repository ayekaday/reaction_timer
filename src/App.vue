<template>
  <h1>How fast can you catch me?</h1>
  <button @click="start" :disabled="isPlaying" class="play">play</button>
  <div v-if="isPlaying">
    <GameBlock :delay="delay" @endGame="endGame" />
  </div>

  <div v-if="end">
    <GameResult :score="score" />
  </div>
</template>

<script>
import GameBlock from "./components/GameBlock.vue";
import GameResult from "./components/GameResult.vue";
export default {
  components: {
    GameBlock,
    GameResult,
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: 0,
      end: false,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 2000 + Math.random() * 5000;
    },
    endGame(score) {
      this.score = score;
      this.isPlaying = false;
      this.end = true;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  color: darkcyan;
}

.play:hover {
  color: rgb(116, 3, 3);
  font-family: cursive;
}
body {
  background-color: floralwhite;
}
</style>
