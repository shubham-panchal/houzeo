<script setup>
import { assets } from "../assets/assets.js";
</script>

<template>
  <div class="header-component">
    <div class="nav--1">
      <img :src="assets?.burgerMenu" class="burger-icon" alt="burger menu" />
      <img :src="assets?.houzeoLogo" alt="houzeo logo" />
      <img :src="assets?.profileIcon" class="profile-icon" alt="profile icon" />
    </div>
    <div class="nav--2">
      <ul class="nav-links-wrapper">
        <li class="nav-link">
          Product
          <img :src="assets?.dropdownArrow" alt="dropdown" />
        </li>
        <li class="nav-link">How Houzeo Works</li>
        <li class="nav-link">Reviews</li>
        <li class="nav-link">
          Buy
          <img :src="assets?.dropdownArrow" alt="dropdown" />
        </li>
        <li class="nav-link">
          Sell
          <img :src="assets?.dropdownArrow" alt="dropdown" />
        </li>
        <li class="nav-link">Pricing</li>
        <li class="nav-link">
          Resources
          <img :src="assets?.dropdownArrow" alt="dropdown" />
        </li>
        <li class="nav-link">Sign In</li>
      </ul>
      <div class="contact-block">
        <p>(844) 448-0110</p>
        <p class="small">(9am to 6pm CST, Mon-Sat)</p>
      </div>
      <button class="cta listing-cta">Start Free Listing</button>
    </div>
  </div>
</template>

<style scoped lang="scss">
@use "../assets/styles/main.scss" as *;

.header-component {
  font-size: 0.875rem;
  padding: 1.42em 1.14em;
  border-bottom: 1px solid $border-color;
  @include flex-container(center, space-between, row);

  .nav--1 {
    flex: 1;
    @include flex-container(center, space-between, row);
  }

  .nav--2 {
    display: none;
  }

  @media (min-width: $breakpoint-lg) {
    padding: 1.42em 1.71em;

    .nav--1 {
      .profile-icon,
      .burger-icon {
        display: none;
      }
    }

    .nav--2 {
      flex: 3.5;
      @include flex-container(center, space-between, row, 1);

      .nav-links-wrapper {
        @include flex-container(center, space-between, row, 1em);

        .nav-link {
          @include flex-container(center, center, row);
          cursor: pointer;
          gap: 0.67em;
        }
      }

      .contact-block {
        .small {
          font-size: 0.75rem;
        }
      }

      .listing-cta {
        font-size: 0.875rem;
        padding: 0.71em 1.14em 0.5em 1.14em;
        border-radius: 0.5em;
        background-image: $primary-gradient;
        color: $white;
        font-weight: $font-medium;
      }
    }
  }
}
</style>
