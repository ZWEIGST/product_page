<template>
    <ProductHeader />
    <ProductCarousel />
    <ProductDescription />
    <div class="product_cards">
        <h2 class="product_cards__heading">ПОХОЖИЕ ТОВАРЫ</h2>
        <ProductCard 
        v-for="(card, index) in productCard"   
            :key="index"   
            :name="card.name"   
            :img="card.img"   
            :price="card.price"   
            :priceOld="card.priceOld"
        />
    </div>
</template>

<script>
import ProductHeader from '@/components/ProductHeader.vue';
import ProductCarousel from '@/components/ProductComp/ProductCarousel.vue';
import ProductDescription from '@/components/ProductComp/ProductDescription.vue';
import ProductCard from '@/components/ProductComp/ProductCard.vue';

    export default {
        name: 'ProductPage',
        components: {
            ProductHeader,
            ProductCarousel,
            ProductDescription,
            ProductCard,
        },
        data () {
          return {
          productCard: [
           {name: 'ПЛАТЬЕ С V-ОБРАЗНЫМ ВЫРЕЗОМ, БЕЛЫЙ', img: 'https://i.postimg.cc/bsBKntZ4/Image.png',  price: '14 900 RUB', price_old: '8 000 RUB'},
           {name: 'ЖАКЕТ ДВУБОРТНЫЙ, СЕРО-ГОЛУБОЙ', price: '8900 RUB', img: 'https://i.postimg.cc/v4xCtZ9T/Image2.png'},
           {name: 'ПЛАТЬЕ МАКСИ С ЯРУСАМИ, БЕЛЫЙ', price: '10 500 RUB', img: 'https://i.postimg.cc/KKXwqhrN/Image3'},
           {name: 'КОМБИНЕЗОН СО СТОЙКОЙ, ЧёРНЫЙ', price: '9500 RUB', img: 'https://i.postimg.cc/7CgcjtKy/Image4.png'},
          ],
          }
        }
    }
</script>

<style lang="scss" scoped>
html {
margin: 0;
padding: 0;
box-sizing: border-box;
}

@font-face {
    font-family: Helvetica;
    src: url(/fonts/helvetica_regular.otf);
   }
   h1 {
    font-family: Helvetica;
   }
   .product_cards {
    &__heading {
        font-family: Helvetica;
        font-size: 12px;
        font-weight: 400;
        line-height: 16px;
    }
   }
</style>