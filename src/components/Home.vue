<script setup>
import { assets } from "../assets/assets.js";
import Map from "./Map.vue";
import Listings from "./Listings.vue";
</script>

<template>
  <div class="home-component">
    <section class="section--1"><Map /></section>
    <section class="section--2"><Listings /></section>
  </div>
</template>

<style scoped lang="scss">
@use "../assets/styles/main.scss" as *;

.home-component {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  height: calc(100vh - 212px);

  .section--1 {
    height: 100%;
    display: none;
  }

  .section--2 {
    height: 100%;
    overflow: auto;
  }

  @media (min-width: $breakpoint-md) {
    height: calc(100vh - 160px);
    grid-template-columns: repeat(2, 1fr);

    .section--1 {
      display: block;
      height: 100%;
      overflow: auto;

      &::-webkit-scrollbar {
        display: none;
      }
    }
  }
}
</style>
