<template>
  <div class="product-card__container">
    <a href="">
      <img class="product-card__img" :src="img" alt="product image" />
      <h2 class="product-card__name">{{ name }}</h2>
    </a>
    <p class="product-card__price">{{ price }}</p>
    <p v-if="priceOld" class="product-card__price-old">{{ priceOld }}</p>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: {
    name: String,
    price: String,
    priceOld: String,
    img: String,
  },
};
</script>

<style lang="scss" scoped>
@use "../../assets/styles/var.scss";
.product-card {
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
    color: var.$colorTextMain;
    font-size: 10px;
    line-height: 14px;
    font-weight: 400;
    text-decoration: none;
  }
  &__price {
    color: var.$colorTextMain;
    font-size: 10px;
    line-height: 14px;
  }
  &__price-old {
    text-decoration-line: line-through;
    color: var.$colorTextHelper;
    font-size: 10px;
    line-height: 14px;
  }
}
@media (max-width: 766px) {
  .product-card {
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
    &__name {
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
