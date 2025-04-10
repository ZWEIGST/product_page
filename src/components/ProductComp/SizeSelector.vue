<template>
  <div class="product-size">
    <h4 class="product-size__heading">Размеры</h4>
    <div class="product-size__btns">
      <div class="product-size__choose">
        <button class="product-size__button">XS</button>
        <h4 class="product-size__remainder">мало</h4>
      </div>
      <div class="product-size__choose">
        <button class="product-size__button">S</button>
        <h4 class="product-size__remainder"></h4>
      </div>
      <div class="product-size__choose">
        <button class="product-size__button">M</button>
        <h4 class="product-size__remainder">подписка</h4>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@use "../../assets/styles/var.scss";
.product-size {
  &__heading {
    font-size: 10px;
    font-weight: 400;
    line-height: 14px;
    margin-bottom: 8px;
  }
  &__btns {
    display: flex;
    flex-direction: row;
    gap: 14px;
  }
  &__choose {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  &__button {
    width: 65px;
    height: 31px;
    border: 1px solid rgba(51, 51, 51, 1);
    background-color: rgba(255, 255, 255, 1);
  }
  &__remainder {
    font-size: 10px;
    font-weight: 400;
    line-height: 14px;
    margin-top: 3px;
    justify-content: center;
    color: var.$colorTextHelper;
  }
}
@media (max-width: 766px) {
  .product-size {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: flex-start;

    &__choose {
      display: flex;
      flex-direction: column;
      align-items: center;
      flex: 0 0 calc(33% - 14px);
    }

    &__button {
      width: 80px;
      margin: 0;
    }
  }
}
</style>
