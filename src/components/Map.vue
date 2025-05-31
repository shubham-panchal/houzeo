<script setup>
import { assets } from "../assets/assets.js";
</script>

<template>
  <div class="map-component">
    <img :src="assets?.mapImage" class="map" alt="map" />
  </div>
</template>

<style scoped lang="scss">
@use "../assets/styles/main.scss" as *;

.map-component {
  height: 100%;
  @include flex-container();

  .map {
    height: 100%;
    width: 100%;
    object-fit: cover;
  }
}
</style>
