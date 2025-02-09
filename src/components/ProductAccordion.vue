<template>
<div class="product_accordion" id="accordion">
     
     <div class="product_accordion__item">
              
     <h3 class="product_accordion__item-head" v-on:click="accordion">Описание</h3>
            
     <div class="product_accordion__item-body"></div>
 
         </div>
         <div class="product_accordion__item">
              
              <h3 class="product_accordion__item-head" v-on:click="accordion">Состав и уход</h3>
               
                       
              <div class="product_accordion__item-body"></div>
               
            </div>
      
</div>
</template>

<script>
    export default {
        methods: {
          accordion(event) {
           const head = event.target;
           const body = head.nextElementSibling;
           body.style.display = body.style.display === "none" ? "block" : "none";
           head.classList.toggle("active");
    },
  },
    }
</script>

<style lang="scss" scoped>
.product_accordion {
   &__item {
    border-bottom: 1px solid rgba(224, 224, 224, 1);
    cursor: pointer;
    &:first-child {
        border-top: 1px solid rgba(224, 224, 224, 1); 
        margin-top: 40px;
    }
    &-head {
        font-size: 10px;
        font-family: Helvetica;
        font-weight: 400;
        line-height: 14px;
        color: rgba(51, 51, 51, 1);
        position: relative;
    &::after {
        content: '+';
        color: rgba(189, 189, 189, 1);
        position: absolute;
        right: 15px;
        top: 50%;
        transform: translateY(-50%);
        font-size: 14px;
        transition: transform 0.3s ease;
    }
    &.active::after {
        transform: translateY(-50%) rotate(45deg);
    }
    }
    &-body {
    display: none;
    font-size: 20px;
    }
   } 
}
@media  (max-width: 766px) {
 .product_accordion {
    align-items: flex-start;
    width: 100%;
    &__item {
        margin-right: 23px;
        width: 100%;
        &:first-child {
            margin-top: 32px;
        }
    }
    &-body {
    display: none;
    font-size: 20px;
    }
  } 
}
</style>