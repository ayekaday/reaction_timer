<template>
  <div class="block">Click Here {{ delay }}</div>
</template>

<script>
export default {
  props: ["delay"],
};
</script>

<style>
.block {
  background-color: coral;
  width: 200px;
  margin: 100px auto;
  padding: 200px;
}
</style>
