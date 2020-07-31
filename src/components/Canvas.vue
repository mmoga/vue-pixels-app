<template>
  <div class="canvas">
    <Pixel v-for="n in 30*30" color="blue" :key="n"/>
  </div>
</template>

<script>
import Pixel from "./Pixel";

export default {
  name: "Canvas",
  components: {
    Pixel
  }
};
</script>

<style lang="stylus" scoped>
.canvas {
  display: flex;
  flex-wrap: wrap;
  max-width: 900px;
}
</style>

