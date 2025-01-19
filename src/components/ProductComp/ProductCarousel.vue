<template>  
    <div class="carousel">  
      <div class="carousel-inner">  
        <div  
          class="carousel-item"  
          :class="{ active: index === currentIndex }"  
          v-for="(image, index) in images"  
          :key="image.id"  
        >  
          <img :src="image.src" :alt="image.alt" />  
        </div>  
      </div>  
      <button @click="prev" class="carousel-control prev">❮</button>  
      <button @click="next" class="carousel-control next">❯</button>  
    </div>  
  </template>  
  
  <script>  
  export default {  
    data() {  
      return {  
        currentIndex: 0,  
        images: [  
          { id: 1, src: 'https://i.postimg.cc/WF59PBrx/Gallery-Big.png', alt: 'product image' },  
          { id: 2, src: 'https://i.postimg.cc/fSk8W8fy/Gallery-small-2.png', alt: 'product image' },  
          { id: 3, src: 'https://i.postimg.cc/7bLsNLr4/Gallery-small-3.png', alt: 'product image' },  
        ],  
      }  
    },  
    methods: {  
      next() {  
        this.currentIndex = (this.currentIndex + 1) % this.images.length;  
      },  
      prev() {  
        this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;  
      },  
    },  
  }  
  </script>  
  
  <style scoped>  
  .carousel {  
    position: relative;  
    width: 100%;  
    overflow: hidden;  
  }  
  
  .carousel-inner {  
    display: flex;  
    transition: transform 0.5s ease-in-out;  
    transform: translateX(-{{ currentIndex * 100 }}%);  
  }  
  
  .carousel-item {  
    max-width: 518px; 
    max-height: 693px; 
    box-sizing: border-box;  
  }  
  
  .carousel img {  
    width: 100%;  
    height: auto;  
  }  
  
  .carousel-control {  
    position: absolute;  
    top: 50%;  
    transform: translateY(-50%);  
    background: rgba(255, 255, 255, 0.7);  
    border: none;  
    padding: 10px;  
    cursor: pointer;  
  }  
  
  .prev {  
    left: 10px;  
  }  
  
  .next {  
    right: 10px;  
  }  
  </style>