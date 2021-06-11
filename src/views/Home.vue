<template>
  <img :src="image" />
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      image:
        "https://www.apple.com/105/media/us/airpods-pro/2019/1299e2f5_9206_4470_b28e_08307a42f19b/anim/sequence/large/01-hero-lightpass/0001.jpg",
    };
  },
};
</script>

<style scoped>
img {
  position: fixed;
  left: 50%;
  top: 50%;
  width: 100%;
  height: auto;
  transform: translate(-50%, -50%);
}
</style>
