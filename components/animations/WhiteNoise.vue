<template>
  <div class="noise-block">
    <canvas id="noisy-canvas"></canvas>
  </div>
</template>

<script>

const createNoise = (time) => {
  let canvas = document.getElementById('noisy-canvas'),
    ctx = canvas.getContext('2d'),
    intTime = 20,
    animationFnRes;

  function getRandom() {
    return Math.random() * 255;
  }

  function render() {
    let imageData = ctx.createImageData(ctx.canvas.width, ctx.canvas.height);
    for (let i = 0; i < imageData.data.length; i += 4) {
      const color = getRandom();
      imageData.data[i] = color;
      imageData.data[i + 1] = color;
      imageData.data[i + 2] = color;
      imageData.data[i + 3] = 255;
    }
    ctx.putImageData(imageData, 0, 0);
  }

  function updateCanvasSize() {
    ctx.canvas.height = canvas.offsetHeight;
    ctx.canvas.width = canvas.offsetWidth;
    requestAnimationFrame(render);
  }

  function timeoutGo() {
    if (intTime < 500) {
      setTimeout(() => {
        requestAnimationFrame(render);
        timeoutGo();
        intTime += 8;
      }, intTime)
    }
  }

  window.addEventListener('resize', updateCanvasSize);
  updateCanvasSize();
  // render(time);
  animationFnRes = setInterval(() => {
    requestAnimationFrame(render), intTime
  });
  setTimeout(() => {
    clearInterval(animationFnRes);
    timeoutGo();
  }, time)
};

export default {
  name: 'WhiteNoise',
  props: {
    time: {
      type: Number,
      default: 2
    }
  },
  mounted: () => {
    createNoise(7 * 1000);
  }
}
</script>

<style lang="scss">
.noise-block {
  height: 100%;
  width: 100%;
}

#noisy-canvas {
  width: 100%;
  height: 100%;
}
</style>
