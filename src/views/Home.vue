<template>
  <canvas id="appleCanvas" />
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      canvas: null,
      context: null,
    };
  },
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
  mounted() {
    const c = document.getElementById("appleCanvas");
    const ctx = c.getContext("2d");
    this.canvas = c;
    this.context = ctx;

    this.drawImage(
      `https://www.apple.com/105/media/us/airpods-pro/2019/1299e2f5_9206_4470_b28e_08307a42f19b/anim/sequence/large/01-hero-lightpass/0001.jpg`
    );
  },
  unmounted() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      const frameCount = 148;
      const scrollFraction = window.scrollY / window.innerHeight;

      const frameIndex = Math.min(
        frameCount - 1,
        Math.floor(scrollFraction * frameCount)
      );

      this.drawImage(
        `https://www.apple.com/105/media/us/airpods-pro/2019/1299e2f5_9206_4470_b28e_08307a42f19b/anim/sequence/large/01-hero-lightpass/${frameIndex
          .toString()
          .padStart(4, "0")}.jpg`
      );
    },
    drawImage(imageSrc) {
      const self = this;
      const image = new Image();
      image.src = imageSrc;

      image.onload = function () {
        self.canvas.height = image.height;
        self.canvas.width = image.width;
        self.context.drawImage(image, 0, 0);
      };
    },
  },
};
</script>

<style scoped>
canvas {
  position: fixed;
  z-index: -1;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}
</style>
