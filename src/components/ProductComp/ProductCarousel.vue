<template>  
    <div class="carousel">  
      <div class="carousel_inner"
           :style="{ transform: `translateX(-${currentIndex * 100}%)` }">  
        <div  
          class="carousel_item"  
          :class="{ active: index === currentIndex }"  
          v-for="(image, index) in images"  
          :key="image.id"  
        >  
          <img :src="image.src" :alt="image.alt" class="carousel_img"/>  
        </div>  
      </div>  
      <button @click="prev" class="carousel_control prev">←</button>  
      <button @click="next" class="carousel_control next">→</button>

      <div class="carousel_indicators" v-show="isMobile">
      <button class="carousel_indicators__btn"
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
          { id: 1, src: 'https://i.postimg.cc/sGFWVnbp/Gallery-Big.png', alt: 'product image' },    
        ],  
        isMobile: false,
      }
    },  
    methods: {  
      next() {  
        this.currentIndex = (this.currentIndex + 1) % this.images.length;  
      },  
      prev() {  
        this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;  
      },  
      goTo(index) {  
        this.currentIndex = index;  // <- Добавлена точка с запятой (опционально)
      },  
      checkMobile() {  
        this.isMobile = window.innerWidth <= 766;  
      },  
    },  
    mounted() {  
      this.checkMobile();  
      window.addEventListener('resize', this.checkMobile);  
    },  
    beforeUnmount() {  
      window.removeEventListener('resize', this.checkMobile);  
    },  
  }  
  </script>
  
  <style lang="scss" scoped>  
  .carousel {  
    position: relative;  
    max-width: 518px; 
    height: 693px;  
    overflow: hidden;  
  &_indicators {
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
  .carousel_indicators__btn:active {
    background: rgba(255, 255, 255, 0.9);
    transform: scale(1.2);
  }
  .carousel_indicators__btn:focus {
  outline: 2px solid rgba(255, 255, 255, 0.8);
  }
  .carousel_inner {  
    display: flex;  
    transition: transform 0.5s ease-in-out;
    object-fit: cover;  
  }  
  
  .carousel_item {  
    box-sizing: border-box;  
    max-width: 100%;
  }  
  
  .carousel_img {    
    height: 693px; 
    object-fit: cover;  
    width: 100%;
  }  
  
  .carousel_control {  
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
  </style>