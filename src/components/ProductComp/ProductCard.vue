<template>
    <div class="product_card__container">
        <a href=""><img class="product_card__img" :src=img alt="product image">
        <h2 class="product_card__name">{{ name }}</h2></a>
        <p class="product_card__price">{{ price }}</p>
        <p  v-if="priceOld" class="product_card__price-old">{{ priceOld }}</p>
    </div>
</template>

<script>
    export default {
        name: 'ProductCard',
          props: {
            name: String,
            price: String,
            priceOld: String,
            img: String,
        },
    }
</script>

<style lang="scss" scoped>
* {  
    margin: 0;  
    padding: 0;  
    box-sizing: border-box;
}
@font-face {
    font-family: Helvetica;
    src: url(/fonts/helvetica_regular.otf);
   }
   h1, h2, h3 {
    font-family: Helvetica;
   }
a {
    text-decoration: none;
}
.product_card {
 &__container {
  display: grid;
  grid-template-rows: auto;
  margin-bottom: 7px;
  row-gap: 9px;
  box-sizing: border-box;
  &:first-child {
    margin-left: 40px;
  }

  &:last-child {
    margin-right: 40px;
 }
}

 &__img {
   height: 444px;
   width: 100%;
   object-fit: cover;
 }
 &__name {
    color:rgba(51, 51, 51, 1);
    font-size: 10px;
    line-height: 14px;
    font-weight: 400;
    text-decoration: none;
    font-family: Helvetica;
 }
 &__price {
    color:rgba(51, 51, 51, 1);
    font-size: 10px;
    line-height: 14px;
 }
 &__price-old {
    text-decoration-line: line-through;
    color: rgba(130, 130, 130, 1);
    font-size: 10px;
    line-height: 14px;
 }
}
@media  (max-width: 766px) {
  .product_card {
  &__container {
   width: 100%;
   height: auto;
   &:first-child {
    margin-left: 0;
  }

  &:last-child {
    margin-right: 0;
 }
  }
  &__heading {
    margin-top: 9px;
  }
  &__img {
    height: auto;
    aspect-ratio: 3/5;
    object-fit: cover;
    width: 100%;
    object-fit: cover;
    display: block;
  }
  }
}
</style>