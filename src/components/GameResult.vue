<template>
  <p>The result is {{ score }}ms.</p>
  <div v-if="score <= 200">
    <h1>Amazing! 🎈🎉🎊</h1>
  </div>
  <div v-else-if="score > 200 && score < 400">
    <h1>As usual. 💪💪</h1>
  </div>
  <div v-else>
    <h1>It's very slow. Try again! 😢😢</h1>
  </div>
</template>

<script>
export default {
  props: ["score"],
};
</script>

<style scoped>
h1 {
  color: crimson;
}
p {
  color: royalblue;
  font-size: medium;
  font-style: italic;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}
</style>
