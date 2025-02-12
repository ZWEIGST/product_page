<template>
  <div class="product-accordion" id="accordion">
    <div class="product-accordion__item">
      <h3
        class="product-accordion__item-head"
        v-on:click="handleAccordionClick"
      >
        Описание
      </h3>
      <div class="product-accordion__item-body"></div>
    </div>
    <div class="product-accordion__item">
      <h3
        class="product-accordion__item-head"
        v-on:click="handleAccordionClick"
      >
        Состав и уход
      </h3>
      <div class="product-accordion__item-body"></div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    handleAccordionClick(event) {
      const head = event.target;
      const body = head.nextElementSibling;
      body.style.display = body.style.display === "none" ? "block" : "none";
      head.classList.toggle("active");
    },
  },
};
</script>

<style lang="scss" scoped>
@use '../../assets/styles/var.scss';
.product-accordion {
    display: flex;
    flex-direction: column;
   &__item {
    border-bottom: 1px solid rgba(224, 224, 224, 1);
    cursor: pointer;
    &:first-child {
        border-top: 1px solid rgba(224, 224, 224, 1); 
        margin-top: 40px;
    }
    &-head {
        font-size: 10px;
        font-weight: 400;
        line-height: 14px;
        color: var.$colorTextMain;
        position: relative;
        text-transform: uppercase;
        padding: 14px 0px 12px 0px;
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
        right: 15px;
        font-size: 14px;
    }
    }
    &-body {
    font-size: 20px;
    }
   } 
}
@media  (max-width: 766px) {
 .product-accordion {
    align-items: flex-start;
    width: 100%;
    &__item {
        margin-right: 23px;
        width: 100%;
        &:first-child {
            margin-top: 32px;
        }
        &-body {
        display: none;
        font-size: 20px;
        }
    } 
 }
}
</style>
