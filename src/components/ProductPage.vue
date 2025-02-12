<template>
  <ProductPageHeader />
  <div class="product-container">

    <div class="product-carousel_container">
      <ProductCarousel />
      <ProductDescription />
    </div>
  </div>
  <div class="product-cards">
    <h2 class="product-cards__heading">ПОХОЖИЕ ТОВАРЫ</h2>
    <div class="product-cards__container">
      <ProductCard
        v-for="(card, index) in productCard"
        :key="index"
        :name="card.name"
        :img="card.img"
        :price="card.price"
        :priceOld="card.priceOld"
      />
    </div>
  </div>
</template>

<script>
import ProductPageHeader from "@/components/ProductComp/ProductPageHeader.vue";
import ProductCarousel from "@/components/ProductComp/ProductCarousel.vue";
import ProductDescription from "@/components/ProductComp/ProductDescription.vue";
import ProductCard from "@/components/ProductComp/ProductCard.vue";

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
      productCard: [
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
      isDesktop: false,
    };
  },
  mounted() {
    this.checkViewport();
    window.addEventListener("resize", this.checkViewport);
  },
  beforeUnmount() {
    window.removeEventListener("resize", this.checkViewport);
  },
  methods: {
    checkViewport() {
      this.isDesktop = window.innerWidth > 766;
    },
  },
};
</script>

<style lang="scss" scoped>
.product-container {
    display: flex;
    justify-content: center;
    flex-direction: row;
    &__gallery {
        display: flex;
        flex-direction: column;
        gap: 4px;
        margin-right: 30px;
    }
    &__img {
        max-width: 70px;
        height: 88px;
    }
}
.product-cards {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    justify-content: center;
    max-width: 1360px;
    &__heading {
        font-family: Helvetica;
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
    &_container {
        display: grid;
        grid-template-columns: 1fr 1fr;
    }
}
@media  (max-width: 766px) {
.product-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    &__gallery {
      display: none;
    }
  }
  .product-carousel_container {
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
      .product_accordion {
      align-self: center;
      &__item {
        margin-left: 16px;
        margin-right: 23px;
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