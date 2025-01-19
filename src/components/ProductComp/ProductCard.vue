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
a {
    text-decoration: none;
}
.product_card {
 &__container {
  display: flex;
  flex-direction: column;
 }

 &__img {
   height: 444px;
 }
 &__name {
    color:rgba(51, 51, 51, 1);
    font-size: 12px;
    line-height: 14px;
    text-decoration: none;
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
</style>