<template>  
    <div class="carousel">  
      <div class="carousel-inner">  
        <div  
          class="carousel-item"  
          :class="{ active: index === currentIndex }"  
          v-for="(image, index) in images"  
          :key="image.id"  
        >  
          <img :src="image.src" :alt="image.alt" class="carousel_img"/>  
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
    max-width: 518px; 
    height: 693px;  
    overflow: hidden;  
  }  
  
  .carousel-inner {  
    display: flex;  
    transition: transform 0.5s ease-in-out;  
    transform: translateX(-{{ currentIndex * 100 }}%);  
  }  
  
  .carousel-item {  

    box-sizing: border-box;  
  }  
  
  .carousel_img {    
    height: 693px;   
    width: 100%;
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