<template>
  <div class="product-header">
    <div class="product-header__logo">
      <img
        src="https://i.postimg.cc/kXcBHFLw/Screenshot-2022-11-15-at-13-25-2.png"
        alt="logo stik"
      />
    </div>
    <div class="product-header__nav">
      <div class="product-header__nav-search">
        <a href="">
          <img :src="ProductHeaderNavSearch" alt="search" />
        </a>
      </div>
      <div v-show="isDesktop" class="product-header__nav-favorite">
        <a href="">
          <img :src="ProductHeaderNavFavorite" alt="favorite" />
        </a>
      </div>
      <div class="product-header__nav-cab">
        <a href="">
          <img :src="ProductHeaderNavCab" alt="cab" />
        </a>
      </div>
      <div class="product-header__nav-cart">
        <a href="">
          <img :src="ProductHeaderNavCart" alt="cab" />
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import { MIN_DESKTOP_SCREEN_WIDTH } from "@/ProductPage/constants";

import ProductHeaderNavCab from "@/assets/icons/ProductHeaderNavCab.svg";
import ProductHeaderNavCart from "@/assets/icons/ProductHeaderNavCart.svg";
import ProductHeaderNavFavorite from "@/assets/icons/ProductHeaderNavFavorite.svg";
import ProductHeaderNavSearch from "@/assets/icons/ProductHeaderNavSearch.svg";

export default {
  data() {
    return {
      isDesktop: false,
      ProductHeaderNavCab,
      ProductHeaderNavCart,
      ProductHeaderNavFavorite,
      ProductHeaderNavSearch,
    };
  },
  mounted() {
    this.checkViewport();
    window.addEventListener("resize", this.checkViewport);
  },
  beforeUnmount() {
    window.removeEventListener("resize", this.checkViewport);
  },
  methods: {
    checkViewport() {
      this.isDesktop = window.innerWidth > MIN_DESKTOP_SCREEN_WIDTH;
    },
  },
};
</script>

<style lang="scss" scoped>
@use "../../assets/styles/var.scss";
.product-header {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  width: 100%;
  &__logo {
    position: absolute;
    left: calc(50% - 56.65px / 2);
    margin: 31px 0 31px 0;
  }
  &__nav {
    display: flex;
    flex-direction: row;
    position: relative;
    margin: 33px 48px 33px 0;
    gap: 16px;
  }
}
@media (max-width: 766px) {
  .product-header {
    display: flex;
    flex-direction: row;
    position: relative;
    justify-content: space-between;
    width: 100%;
    padding: 0 16px;

    &__logo {
      position: absolute;
      left: calc(50% - 38px / 2);
      margin: 17px 0 16px 0;
    }

    &__nav {
      width: 100%;
      margin: 20px 0;
      justify-content: space-between;
      margin: 15px 15px 16px;

      &-cab {
        order: -1;
      }
      a:first-child,
      a:nth-child(2) {
        margin-right: auto;
      }
      &-cart {
        margin-left: auto;
      }
    }
  }
}
</style>
