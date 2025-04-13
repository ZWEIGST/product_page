<template>
  <ProductPageHeader />

  <div class="product-page__container">
    <div class="product-carousel__container">
      <ProductCarousel
        v-for="(card, index) in ProductCarousel"
        :key="index"
        :name="card.name"
        :img="card.img"
        :price="card.price"
        :price-old="card.priceOld"
      />
      <ProductDescription />
    </div>

    <div class="product-cards">
      <h2 class="product-cards__heading">ПОХОЖИЕ ТОВАРЫ</h2>
      <div class="product-cards__container">
        <ProductCard
          v-for="(card, index) in suggestedProducts"
          :key="index"
          :name="card.name"
          :img="card.img"
          :price="card.price"
          :price-old="card.priceOld"
        />
      </div>
    </div>
  </div>
</template>

<script>
import ProductPageHeader from "./components/ProductPageHeader.vue";
import ProductCarousel from "./components/ProductCarousel.vue";
import ProductDescription from "./components/ProductDescription.vue";
import ProductCard from "./components/ProductCard.vue";

export default {
  name: "ProductPage",
  components: {
    ProductPageHeader,
    ProductCarousel,
    ProductDescription,
    ProductCard,
  },
  data() {
    return {
      suggestedProducts: [
        {
          name: "ПЛАТЬЕ С V-ОБРАЗНЫМ ВЫРЕЗОМ, БЕЛЫЙ",
          img: "https://i.postimg.cc/bsBKntZ4/Image.png",
          price: "14 900 RUB",
          priceOld: "8 000 RUB",
        },
        {
          name: "ЖАКЕТ ДВУБОРТНЫЙ, СЕРО-ГОЛУБОЙ",
          price: "8900 RUB",
          img: "https://i.postimg.cc/v4xCtZ9T/Image2.png",
        },
        {
          name: "ПЛАТЬЕ МАКСИ С ЯРУСАМИ, БЕЛЫЙ",
          price: "10 500 RUB",
          img: "https://i.postimg.cc/cv1n4tk5/Image3.png",
        },
        {
          name: "КОМБИНЕЗОН СО СТОЙКОЙ, ЧёРНЫЙ",
          price: "9500 RUB",
          img: "https://i.postimg.cc/7CgcjtKy/Image4.png",
        },
      ],
      ProductCarousel: [
        {
          name: "ПЛАТЬЕ С V-ОБРАЗНЫМ ВЫРЕЗОМ, БЕЛЫЙ",
          img: "https://i.postimg.cc/5yYLGC7D/Gallery-Big.png",
          price: "14 900 RUB",
          priceOld: "8 000 RUB",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.product-page__container {
  max-width: 1360px;
}
.product-carousel__container {
  display: flex;
  justify-content: center;
}
.product-cards {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: center;
  &__heading {
    font-size: 12px;
    font-weight: 400;
    line-height: 16px;
    margin: 42px 0px 31px 40px;
  }
  &__container {
    display: flex;
    flex-direction: row;
    gap: 8px;
  }
}
.product-carousel {
  &__container {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
}
@media (max-width: 766px) {
  .product-carousel__container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 31px;
  }
  .product-cards {
    &__container {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 32px 8px;
      margin-left: 16px;
      margin-right: 16px;
      box-sizing: border-box;
      grid-auto-rows: auto;
    }
    &__heading {
      margin-left: 16px;
    }
  }
}
</style>
