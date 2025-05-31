<script setup>
import { assets } from "../assets/assets.js";
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation, Pagination } from "swiper/modules";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

const slides = [
  assets?.carouselImage1,
  assets?.carouselImage2,
  assets?.carouselImage3,
  assets?.carouselImage4,
];

const propertyData = [
  {
    _id: 1,
    propertyType: "House For Sale",
  },
  {
    _id: 2,
    propertyType: "Condo For Sale",
  },
  {
    _id: 3,
    propertyType: "Multi-family home For Sale",
  },
  {
    _id: 4,
    propertyType: "House For Sale",
  },
  {
    _id: 5,
    propertyType: "Condo For Sale",
  },
  {
    _id: 6,
    propertyType: "Multi-family home For Sale",
  },
];
</script>

<template>
  <div class="listings-component">
    <div class="results-block">
      <div class="search-text">Austin, TX real estate & homes for sale</div>
      <div class="wrapper">
        <div class="sub-text">2,010 Homes</div>
        <div class="sortby-block">
          <p class="sub-text">Sort By:</p>
          <div class="dropdown">
            <div class="selected-option-wrapper">
              <p class="selected-option">New Listing</p>
            </div>
            <img :src="assets?.dropdownArrow" alt="dropdown arrow" />
          </div>
        </div>
      </div>
    </div>
    <div class="cards-block">
      <div class="cards" v-for="data in propertyData" :key="data?._id">
        <div class="image-wrapper">
          <swiper
            :modules="[Navigation, Pagination]"
            navigation
            pagination
            class="custom-swiper"
          >
            <swiper-slide
              v-for="(slide, index) in slides"
              :key="index"
              class="custom-swiper-slide"
            >
              <img :src="slide" class="carousel-image" alt="carousel image" />
            </swiper-slide>
          </swiper>
        </div>
        <div class="body-wrapper">
          <div class="top">
            <div class="sale-tag">
              <div class="dot"></div>
              House for sale
            </div>
            <p class="top-text">
              <img :src="assets?.eyeIcon" alt="views" /> 2.3K
            </p>
          </div>
          <div class="middle">
            <p class="price">$3,349,000</p>
            <div class="details">
              <p><span>4</span> Beds</p>
              <p><span>3</span> Baths</p>
              <p><span>998</span> sqft.</p>
            </div>
          </div>
          <p class="address">
            <span>2856 Meadow Park Ave</span>, Henderson, NV 89052
          </p>
          <p class="address">
            Nashville (Real Tracs Mid) MLS-TN as distributed by MLS GRID
          </p>
        </div>
        <div class="card-overlay">
          <div class="onmarket-tag">6 days on Houzeo</div>
          <div class="heart-icon-wrapper">
            <img :src="assets?.heartIcon" class="heart-icon" alt="like card" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
@use "../assets/styles/main.scss" as *;

.listings-component {
  padding: 1.25rem 1em;

  .results-block {
    @include flex-container(normal, normal, column, 0.375em);
    .search-text {
      font-size: 1.125rem;
      font-weight: $font-semibold;
    }
    .wrapper {
      @include flex-container(center, space-between, row);
      font-size: 0.875rem;
      color: $black-40;

      .sortby-block,
      .dropdown {
        @include flex-container(center, space-between, row, 0.5em);
      }

      .selected-option {
        color: $primary-blue;
        font-weight: $font-medium;
      }
    }
  }

  .cards-block {
    padding: 1.25em 0;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(288px, 1fr));
    box-sizing: border-box;
    gap: 1.25rem;

    .cards {
      border: 1px solid #0000001a;
      box-shadow: 0px 0px 20px 0px #00000033;
      cursor: pointer;
      position: relative;

      &:hover {
        transform: scale(1.01);
        box-shadow: 0 3px 5px #00000026;
        transition: transform 0.2s ease-in-out;
      }
      border-radius: 1rem;

      .image-wrapper {
        width: 100%;
        .carousel-image {
          width: 100%;
          max-height: 192px;
          overflow: hidden;
          object-fit: cover;
          object-position: top center;
        }
      }

      .body-wrapper {
        @include flex-container(normal, normal, column, 0.67em);
        font-size: 0.75rem;
        padding: 1em;

        .top {
          @include flex-container(center, space-between, row);
          .top-text {
            @include flex-container(center, center, row);
          }
          .sale-tag {
            @include flex-container(center, normal, row, 0.67em);
            border: 1px solid $border-color;
            border-radius: 10em;
            padding: 0.5em 0.67em;

            .dot {
              width: 1em;
              height: 1em;
              border-radius: 50%;
              background-color: #00b67b;
            }
          }
        }
        .middle {
          @include flex-container(center, space-between, row);
          .price {
            font-size: 1.125rem;
            color: $primary-blue;
            font-weight: $font-semibold;
          }
          .details {
            @include flex-container(center, space-between, row, 1em);
            color: $black-40;

            span {
              color: $primary-blue;
              font-weight: $font-medium;
            }
          }
        }
        .address {
          color: $black-40;
          span {
            color: $primary-black;
          }
        }
      }

      .card-overlay {
        padding: 0.5em;
        position: absolute;
        inset: 0;
        z-index: 99;
        @include flex-container(flex-start, space-between, row);

        .onmarket-tag {
          margin: 0.83em;
          font-size: 0.75rem;
          font-weight: $font-medium;
          @include flex-container(center, normal, row, 0.67em);
          border: 1px solid $border-color;
          border-radius: 10em;
          padding: 0.5em 0.67em;
          background-color: $white;
          box-shadow: 0 4px 10px 0 $drop-shadow-color;
        }

        .heart-icon-wrapper {
          @include flex-container(center, center, row);
          width: max-content;
          height: max-content;
          border: 10px solid transparent;

          &:hover {
            border-color: $primary-blue;
            border-radius: 50%;
            background-color: $white;
            box-shadow: 0px 0px 10px 10px $primary-blue;
            animation: pulse 1s infinite;

            .heart-icon {
              border-radius: inherit;
              box-shadow: 0px 0px 10px 10px $primary-blue;
              animation: pulse 1.5s infinite;
            }
          }
        }
      }
    }
  }

  @media (min-width: $breakpoint-md) {
    .cards-block {
      height: 100%;
      overflow-y: auto;
      overflow-x: hidden;

      &::-webkit-scrollbar {
        display: none;
      }
    }
  }
}
</style>
