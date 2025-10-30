
<script setup>
  const img1 = "https://wallpapers.com/images/high/aot-pictures-28vwnt1csr51vhrj.webp";
  const img2 = "https://img.goodfon.com/wallpaper/nbig/8/17/anime-cyberpunk-edgerunners-hd-wallpaper.webp";
  const gosta = false;
  const gosta2 = false;
</script>

<template>
  <img v-if="gosta" :src="img1" alt="">
  <img v-else-if="gosta2" :src="img2 " alt="">
  <h2 v-else>Burro</h2>
</template>

<style scoped>
  img {
    max-width: 480px;
  }
</style>
