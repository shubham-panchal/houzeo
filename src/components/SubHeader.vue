<script setup>
import { assets } from "../assets/assets.js";
</script>

<template>
  <div class="subheader-component">
    <div class="group--1">
      <div class="search-block">
        <input type="text" class="input-field" placeholder="Austin, TX" />
        <img :src="assets?.crossIcon" alt="clear input icon" />
        <img :src="assets?.searchIcon" alt="search icon" />
      </div>
      <div class="mobile-filter-icon-wrapper">
        <img :src="assets?.mobileFilterIcon" alt="filter icon" />
      </div>
    </div>
    <div class="group--2">
      <div class="filters-block">
        <div class="dropdowns">
          <div class="dropdown-selected">
            <p>For Sale</p>
            <img :src="assets?.dropdownArrow" alt="dropdown arrow" />
          </div>
          <div class="dropdown-options-wrapper">
            <ul class="dropdown-options">
              <li class="option">For Sale</li>
              <li class="option">Sold</li>
            </ul>
          </div>
        </div>
        <div class="dropdowns">
          <div class="dropdown-selected">
            <p>Price</p>
            <img :src="assets?.dropdownArrow" alt="dropdown arrow" />
          </div>
          <div class=""></div>
          <div class="dropdown-options-wrapper">
            <ul class="dropdown-options">
              <li class="option">For Sale</li>
              <li class="option">Sold</li>
            </ul>
          </div>
        </div>
        <div class="dropdowns mobile-hidden">
          <div class="dropdown-selected">
            <p>Beds & Baths</p>
            <img :src="assets?.dropdownArrow" alt="dropdown arrow" />
          </div>
          <div class=""></div>
          <div class="dropdown-options-wrapper">
            <ul class="dropdown-options">
              <li class="option">For Sale</li>
              <li class="option">Sold</li>
            </ul>
          </div>
        </div>
        <div class="dropdowns mobile-hidden">
          <div class="dropdown-selected">
            <p>Property Type</p>
            <img :src="assets?.dropdownArrow" alt="dropdown arrow" />
          </div>
          <div class=""></div>
          <div class="dropdown-options-wrapper">
            <ul class="dropdown-options">
              <li class="option">For Sale</li>
              <li class="option">Sold</li>
            </ul>
          </div>
        </div>
      </div>
      <div class="actions-block">
        <button class="cta filters-cta">
          <img :src="assets?.desktopFilterIcon" alt="filter icon" /> Filters
        </button>
        <button class="cta save-cta">Save Search</button>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
@use "../assets/styles/main.scss" as *;

.subheader-component {
  padding: 1em 1.25em;
  box-shadow: 0 2px 10px 0 $drop-shadow-color;
  @include flex-container(normal, normal, column, 1em);

  .group--1 {
    @include flex-container(center, space-between, row, 1em);
    .search-block {
      @include flex-container(center, normal, row);
      flex: 1;
      border-radius: 10em;
      padding: 0.5em 0.5em 0.5em 1em;
      border: 2px solid $border-color;
      box-sizing: border-box;

      .input-field {
        font-family: $primary-font;
        font-size: 0.875rem;
        width: 100%;
        outline: none;
        border: none;
        font-weight: $font-medium;
      }

      &:hover,
      &:active {
        border: 2px solid $primary-blue;
      }
    }
  }

  .group--2 {
    @include flex-container(center, space-between, row, 1em);

    .filters-block {
      @include flex-container(center, normal, row, 1em);
      .mobile-hidden {
        display: none;
      }
      .dropdowns {
        position: relative;
        font-size: 0.75rem;
        padding: 1em 1em 1em 1.16em;
        border: 1px solid $border-color;
        border-radius: 0.67em;
        cursor: pointer;

        &:hover {
          border: 1px solid $primary-blue;
        }

        .dropdown-selected {
          @include flex-container(center, space-between, row, 1em);
        }

        .dropdown-options-wrapper {
          padding-top: 1em;
          position: absolute;
          top: 100%;
          left: 0;
          right: 0;
          display: none;

          .dropdown-options {
            width: 12em;
            max-width: 12em;
            box-shadow: 0 2px 10px 0 $drop-shadow-color;
            background-color: $white;
            border-radius: 0.67em;
            border: 1px solid $border-color;
            overflow: hidden;

            .option {
              padding: 1em;
              border-bottom: 1px solid $border-color;

              &:last-child {
                border: none;
              }

              &:hover {
                background-image: $primary-gradient;
                color: $white;
              }
            }
          }
        }
        &:hover {
          .dropdown-options-wrapper {
            display: block;
          }
        }
      }
    }

    .actions-block {
      @include flex-container(center, flex-start, row, 1em);
      .save-cta {
        font-size: 0.75rem;
        font-weight: $font-medium;
        padding: 0.75em 1.16em;
        border-radius: 10em;
        color: $white;
        background-color: #0b5aa5;
      }

      .filters-cta {
        font-size: 0.75rem;
        padding: 1em 1em 1em 1.16em;
        border: 1px solid $border-color;
        border-radius: 0.67em;
        cursor: pointer;
        display: none;
        @include flex-container(center, center, row, 0.67em);

        &:hover {
          border-color: $primary-blue;
        }
      }
    }
  }

  @media (min-width: $breakpoint-md) {
    flex-direction: row;
    .group--1 {
      flex: 1;
      .mobile-filter-icon-wrapper {
        display: none;
      }
    }

    .group--2 {
      flex: 2;
      .filters-block {
        .mobile-hidden {
          display: block;
        }
        .dropdowns {
          font-size: 0.875rem;
        }
      }

      .actions-block {
        flex: 1;
        font-size: 0.875rem;

        .save-cta {
          padding: 1em 1.42em;
        }

        .filters-cta {
          font-size: 0.875rem;
          display: flex;
        }
      }
    }
  }
}
</style>
