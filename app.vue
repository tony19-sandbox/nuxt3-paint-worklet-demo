<template>
  <div>
    <button>Click</button>
  </div>
</template>

<script>
import houdiniNoise from './node_modules/houdini-noise/dist/worklet.js?url'

export default {
  mounted() {
    CSS.paintWorklet.addModule(houdiniNoise)
  }
}
</script>

<style scoped>
button {
  --noise: 0;
  --noise-cell-size: 1;
  --noise-hue: 10;
  --noise-saturation: 80;
  --noise-lightness: 10 100;
  background: paint(noise);
  width: 100px;
  height: 2rem;
}
</style>