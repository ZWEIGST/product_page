<template>
    <div class="product_description">
     <h2 class="product_description__heading">ЖАКЕТ УДЛИНЁННЫЙ, БЕЛЫЙ</h2>
     <h3 class="product_description__price">8900 RUB</h3>
     <div class="product_size">
        <h4 class="product_size__heading">Размеры</h4>
        <div class="product_size__btns">
            <div class="product_size__choose">
            <button class="product_size__button">XS</button>
            <h4 class="product_size__remainder">Мало</h4>
        </div>
        <div class="product_size__choose">
            <button class="product_size__button">S</button>
            <h4 class="product_size__remainder"></h4>
        </div>
        <div class="product_size__choose">
            <button class="product_size__button">M</button>
            <h4 class="product_size__remainder">Подписка</h4>
        </div>
        </div>
        <div class="product_color">
            <h4 class="product_color__heading">Цвет: белый</h4>
            <div class="product_color__choose">
                <button class="product_color__btn1"></button>
                <button class="product_color__btn2"></button>
                <button class="product_color__btn3"></button>
            </div>
            <div class="product_cart">
                <button class="product_cart__btn">добавить в корзину</button>
                <button class="product_cart__favorite"><svg class="product_header__nav-favorite" width="11" height="14" viewBox="0 0 11 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M5.38273 10.2994L10.7655 14V0H0V14L5.38273 10.2994ZM0.897121 12.3036L5.38273 8.97606L9.86834 12.3036V0.881352H0.897121V12.3036Z" fill="black"/>
                </svg></button>
            </div>
            <ProductAccordion />
        </div>
     </div>
    </div>
</template>

<script>
import ProductAccordion from '../ProductAccordion.vue';

    export default {
        components: {
            ProductAccordion,
        }
    }
</script>

<style lang="scss" scoped>
.product_description {
    &__heading {
        font-family: Helvetica;
        font-size: 12px;
        font-weight: 400;
        line-height: 16px;
        color: rgba(51, 51, 51, 1);
    }
    &__price {
        font-family: Helvetica;
        font-size: 12px;
        font-weight: 400;
        line-height: 16px;
    }
}
.product_size {
    &__heading {
        font-family: Helvetica;
        font-size: 10px;
        font-weight: 400;
        line-height: 14px;
    }
    &__btns {
        display: flex;
        flex-direction: row;
        gap: 14px;
    }
    &__choose {


    }
    &__button {
        width: 65px;
        height: 31px;
        border: 1px solid rgba(51, 51, 51, 1);
        background-color:  rgba(255, 255, 255, 1);
    }
    &__remainder {
        font-family: Helvetica;
        font-size: 10px;
        font-weight: 400;
        line-height: 14px;
        margin-top: 3px;
    }
}
.product_color {
    &__heading {
        font-family: Helvetica;
        font-size: 10px;
        font-weight: 400;
        line-height: 14px;
    }
    &__choose {
     display: flex;
     flex-direction: row;
     gap: 16px;
    }
    &__btn1 {
          width: 28px;  
          height: 27px;
          background-color: rgba(255, 255, 255, 1);
        }
        &__btn2 {
          width: 28px;  
          height: 27px;
          background-color: rgba(0, 0, 0, 1);          ;
        }
        &__btn3 {
          width: 28px;  
          height: 27px;
          background-color: rgba(249, 241, 220, 1);
        }
}
.product_cart {
    &__btn {
     height: 44px;
     max-width: 306px;
     background-color: rgba(0, 0, 0, 1);
     color:rgba(255, 255, 255, 1);
     font-family: Helvetica;
     font-size: 11px;
     font-weight: 400;
     line-height: 15px;
     margin-right: 10px;
    }
    &__favorite {
        width: 44px;
        height: 44px;
        background-color: rgba(255, 255, 255, 1);
    }
}
</style>