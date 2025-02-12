<template>
  <div class="carousel">
    <div class="product-container__gallery" v-show="isDesktop">
      <img
        src="https://i.postimg.cc/5yYLGC7D/Gallery-Big.png"
        alt="product image"
        class="product-container__img"
      />
      <img
        src="https://i.postimg.cc/fSk8W8fy/Gallery-small-2.png"
        alt="product image"
        class="product-container__img"
      />
      <img
        src="https://i.postimg.cc/7bLsNLr4/Gallery-small-3.png"
        alt="product image"
        class="product-container__img"
      />
    </div>
    <div
      class="carousel__inner"
      :style="{ transform: `translateX(-${currentIndex * 100}%)` }"
    >
      <div
        class="carousel__item"
        :class="{ active: index === currentIndex }"
        v-for="(image, index) in images"
        :key="image.id"
      >
        <img :src="image.src" :alt="image.alt" class="carousel__img" />
      </div>
    </div>
    <button @click="prev" class="carousel__control prev">
      <svg
        width="15"
        height="10"
        viewBox="0 0 15 10"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          fill-rule="evenodd"
          clip-rule="evenodd"
          d="M2.18557e-07 5L5.27542 10L6.24343 9.08253L2.62051 5.64875L15 5.64875L15 4.35125L2.62051 4.35125L6.24343 0.917474L5.27542 -2.30596e-07L2.18557e-07 5Z"
          fill="#BDBDBD"
        />
      </svg>
    </button>
    <button @click="next" class="carousel__control next">
      <svg
        width="15"
        height="10"
        viewBox="0 0 15 10"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          fill-rule="evenodd"
          clip-rule="evenodd"
          d="M15 5L9.72458 10L8.75657 9.08253L12.3795 5.64875L-2.46915e-07 5.64875L-1.90199e-07 4.35125L12.3795 4.35125L8.75657 0.917474L9.72458 -2.30596e-07L15 5Z"
          fill="black"
        />
      </svg>
    </button>

    <div class="carousel-indicators" v-show="isMobile">
      <button
        class="carousel-indicators__btn"
        v-for="(image, index) in images"
        :key="'indicator-' + image.id"
        :class="{ active: index === currentIndex }"
        @click="goTo(index)"
      ></button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentIndex: 0,
      images: [
        {
          id: 1,
          src: "https://i.postimg.cc/5yYLGC7D/Gallery-Big.png",
          alt: "product image",
        },
      ],
      isMobile: false,
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
  },
  mounted() {
    this.checkIfMobile();
    window.addEventListener("resize", this.checkIfMobile);
  },
  beforeUnmount() {
    window.removeEventListener("resize", this.checkIfMobile);
  },
};
</script>

<style lang="scss" scoped>
@use '../../assets/styles/var.scss';
.carousel {  
    position: relative;  
    max-width: 518px; 
    height: 693px;  
    overflow: hidden;  
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
    }
    }
  }  
  .carousel-indicators__btn:active {
    background: rgba(255, 255, 255, 0.9);
    transform: scale(1.2);
  }
  .carousel-indicators__btn:focus {
  outline: 2px solid rgba(255, 255, 255, 0.8);
  }
  .carousel__inner {  
    display: flex;  
    transition: transform 0.5s ease-in-out;
    object-fit: cover;  
  }  
  
  .carousel__item {  
    box-sizing: border-box;  
    max-width: 100%;
  }  
  
  .carousel__img {    
    height: 693px; 
    object-fit: cover;  
    width: 100%;
  }  
  
  .carousel__control {  
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
  }  
  
  .prev {  
    left: 16px; 
    color: rgba(189, 189, 189, 1);
  }  
  
  .next {  
    right: 16px;
    color: rgba(0, 0, 0, 1);
  }  
@media  (max-width: 766px) {
  .carousel {
  display: flex;
  justify-content: center;
  max-width: 100%;
  &__img {
    width:100%;
  }
  }
}
</style>
