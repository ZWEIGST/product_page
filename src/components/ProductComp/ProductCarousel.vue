<template>
  <div class="carousel">
    <div v-show="isDesktop" class="carousel-gallery">
      <img
        src="https://i.postimg.cc/5yYLGC7D/Gallery-Big.png"
        alt="product image"
        class="carousel-gallery__img"
      />
      <img
        src="https://i.postimg.cc/fSk8W8fy/Gallery-small-2.png"
        alt="product image"
        class="carousel-gallery__img"
      />
      <img
        src="https://i.postimg.cc/7bLsNLr4/Gallery-small-3.png"
        alt="product image"
        class="carousel-gallery__img"
      />
    </div>
    <div
      class="carousel__inner"
      :style="{ transform: `translateX(-${currentIndex * 100}%)` }"
    >
      <div
        v-for="(image, index) in images"
        :key="image.id"
        class="carousel__item"
        :class="{ active: index === currentIndex }"
      >
        <img :src="image.src" :alt="image.alt" class="carousel__img" />
      </div>
      <button class="carousel__control carousel__control_prev" @click="prev">
        <img :src="CarouselControlPrev" alt="left arrow" />
      </button>
      <button class="carousel__control carousel__control_next" @click="next">
        <img :src="CarouselControlNext" alt="right arrow" />
      </button>

      <div v-show="isMobile" class="carousel-indicators">
        <button
          v-for="(image, index) in images"
          :key="'indicator-' + image.id"
          class="carousel-indicators__btn"
          :class="{ active: index === currentIndex }"
          @click="goTo(index)"
        ></button>
      </div>
    </div>
  </div>
</template>

<script>
import { MAX_MOBILE_SCREEN_WIDTH } from "@/components/constants";
import { MIN_DESKTOP_SCREEN_WIDTH } from "@/components/constants";

import CarouselControlPrev from "@/assets/icons/CarouselControlPrev.svg";
import CarouselControlNext from "@/assets/icons/CarouselControlNext.svg";

export default {
  data() {
    return {
      currentIndex: 0,
      CarouselControlPrev,
      CarouselControlNext,

      images: [
        {
          id: 1,
          src: "https://i.postimg.cc/5yYLGC7D/Gallery-Big.png",
          alt: "product image",
        },
        {
          id: 2,
          src: "https://i.postimg.cc/fSk8W8fy/Gallery-small-2.png",
          alt: "product image",
        },
        {
          id: 3,
          src: "https://i.postimg.cc/7bLsNLr4/Gallery-small-3.png",
          alt: "product image",
        },
      ],
      isMobile: false,
      isDesktop: false,
    };
  },
  methods: {
    next() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    },
    prev() {
      this.currentIndex =
        (this.currentIndex - 1 + this.images.length) % this.images.length;
    },
    goTo(index) {
      this.currentIndex = index;
    },
    checkIfMobile() {
      this.isMobile = window.innerWidth <= MAX_MOBILE_SCREEN_WIDTH;
    },
    checkViewport() {
      this.isDesktop = window.innerWidth > MIN_DESKTOP_SCREEN_WIDTH;
    },
  },
  mounted() {
    this.checkIfMobile();
    this.checkViewport();
    window.addEventListener("resize", this.checkIfMobile);
    window.addEventListener("resize", this.checkViewport);
  },
  beforeUnmount() {
    window.removeEventListener("resize", this.checkIfMobile);
    window.removeEventListener("resize", this.checkViewport);
  },
};
</script>

<style lang="scss" scoped>
@use "../../assets/styles/var.scss";
.carousel {
  position: relative;
  overflow: hidden;
  display: flex;
  justify-content: center;
  flex-direction: row;
  width: 100%;

  &-gallery {
    display: flex;
    flex-direction: column;
    gap: 4px;
    margin-right: 30px;
    &__img {
      max-width: 70px;
      height: 88px;
    }
  }
  &-indicators {
    position: absolute;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    gap: 6px;
    &__btn {
      width: 7px;
      height: 7px;
      border-radius: 50%;
      border: none;
      background: rgba(255, 255, 255, 0.5);
      cursor: pointer;
      transition: all 0.3s ease;
      padding: 0;
      &:active {
        background: rgba(255, 255, 255, 0.9);
        transform: scale(1.2);
      }
      &:focus {
        outline: 2px solid rgba(255, 255, 255, 0.8);
      }
    }
  }
  &__inner {
    display: flex;
    transition: transform 0.5s ease-in-out;
    object-fit: cover;
    width: 100%;
  }
  &__item {
    box-sizing: border-box;
    max-width: 100%;
    &.active {
      opacity: 1;
    }
  }
  &__img {
    height: 693px;
    max-width: 518px;
    object-fit: cover;
    width: 100%;
  }
  &__control {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: rgba(255, 255, 255, 0.4);
    border: none;
    padding: 10px;
    cursor: pointer;
    width: 32px;
    height: 32px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 10;
    &_prev {
      left: 16px;
      color: rgba(189, 189, 189, 1);
    }
    &_next {
      right: 16px;
      color: rgba(0, 0, 0, 1);
    }
  }
}

@media (max-width: 766px) {
  .carousel {
    display: flex;
    justify-content: center;
    flex-direction: column;
    max-width: 100%;
    &-gallery {
      &__img {
        width: 100%;
      }
    }
  }
}
</style>
