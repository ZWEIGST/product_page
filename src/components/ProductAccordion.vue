<template>
<div class="product_accordion" id="accordion">
     
     <div class="product_accordion__item">
              
     <h3 class="product_accordion__item-head" v-on:click="accordion">
        Описание
             </h3>
      
              
     <div class="product_accordion__item-body"></div>
      
         </div>
         <div class="product_accordion__item">
              
              <h3 class="product_accordion__item-head" v-on:click="accordion">
                Состав и уход
                      </h3>
               
                       
              <div class="product_accordion__item-body"></div>
               
                  </div>
      
     </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
.product_accordion {
   &__item {
    border-bottom: 1px;
    border-top: 1px;
    border-color: rgba(224, 224, 224, 1);
    &-head {
        font-size: 10px;
        font-family: Helvetica;
        font-weight: 400;
        line-height: 14px;
        color: rgba(51, 51, 51, 1);
    }
    &-body {
    
    }
   } 
}
</style>