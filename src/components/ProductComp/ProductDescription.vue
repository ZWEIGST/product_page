<template>
  <div class="product-description">
    <h2 class="product-description__heading">ЖАКЕТ УДЛИНЁННЫЙ, БЕЛЫЙ</h2>
    <p class="product-description__price">8900 RUB</p>
    <div class="product-selector">
      <SizeSelector />
      <ColorPicker />

      <div class="product-cart">
        <button v-show="isDesktop" class="product-cart__btn">
          добавить в корзину
        </button>
        <button class="product-cart__favorite">
          <img :src="ProductDescriptionCartFavorite" alt="favorite" />
        </button>
      </div>

      <ProductAccordion />
    </div>
  </div>
</template>

<script>
import ProductAccordion from "./ProductAccordion.vue";
import SizeSelector from "./SizeSelector.vue";
import ColorPicker from "./ColorPicker.vue";

import { MAX_MOBILE_SCREEN_WIDTH } from "@/components/constants";
import { MIN_DESKTOP_SCREEN_WIDTH } from "@/components/constants";

import ProductDescriptionCartFavorite from "@/assets/icons/ProductDescriptionCartFavorite.svg";

export default {
  components: {
    ProductAccordion,
    SizeSelector,
    ColorPicker,
  },
  data() {
    return {
      isDesktop: false,
      isMobile: false,
      ProductDescriptionCartFavorite,
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
    checkMobile() {
      this.isMobile = window.innerWidth <= MAX_MOBILE_SCREEN_WIDTH;
    },
  },
  checkViewport() {
    this.isDesktop = window.innerWidth > MIN_DESKTOP_SCREEN_WIDTH;
    this.$forceUpdate();
  },
};
</script>

<style lang="scss" scoped>
@use "../../assets/styles/var.scss";
.product-description {
  margin-left: 61px;
  &__heading {
    font-family: Helvetica;
    font-size: 12px;
    font-weight: 400;
    line-height: 16px;
    color: var.$colorTextMain;
    margin-top: 0;
  }
  &__price {
    font-family: Helvetica;
    font-size: 12px;
    font-weight: 400;
    line-height: 16px;
  }
}
.product-selector {
  margin-top: 31px;
}
@keyframes scaleUp {
  from {
    transform: scale(0);
  }
  to {
    transform: scale(1);
  }
}

.product-cart {
  display: grid;
  grid-template-columns: 2fr 1fr;
  margin-top: 36px;
  &__btn {
    height: 44px;
    width: 306px;
    background-color: rgba(0, 0, 0, 1);
    color: rgba(255, 255, 255, 1);
    font-family: Helvetica;
    font-size: 11px;
    font-weight: 400;
    line-height: 15px;
    margin-right: 10px;
    display: block;
    text-transform: uppercase;
    border: none;
    &:hover {
      cursor: pointer;
    }
  }
  &__favorite {
    width: 44px;
    height: 44px;
    background-color: rgba(255, 255, 255, 1);
    border: solid 1px;
    display: flex;
    justify-content: center;
    align-items: center;
    &-inner {
      position: absolute;
      &:hover {
        cursor: pointer;
      }
    }
  }
}

@media (max-width: 766px) {
  .product-cart__btn {
    display: none;
  }
  .product-description {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    width: calc(100% - 16px);
    margin-left: 16px;

    &__price {
      width: 100%;
    }
  }

  .product-size {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: flex-start;

    &__btns {
      flex-wrap: wrap;
      justify-content: flex-start;
      row-gap: 14px;
    }

    &__choose {
      display: flex;
      flex-direction: column;
      align-items: center;
      flex: 0 0 calc(33% - 14px);
    }

    &__button {
      width: 80px;
      margin: 0;
    }
  }

  .product-cart {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;

    &__btn {
      display: none;
    }

    &__favorite {
      right: 0;
      margin: 0;
      border: none;
      width: 44px;
      height: 44px;
      background-color: rgba(255, 255, 255, 1);
    }
  }
}
</style>
