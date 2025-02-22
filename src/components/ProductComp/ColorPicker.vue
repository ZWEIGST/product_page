<template>
  <div class="product-color">
    <h4 class="product-color__heading">Цвет: {{ selectedColor }}</h4>
    <div class="product-color__choose">
      <ColorButton
        v-for="(color, index) in colors"
        :key="index"
        :color="color"
        @select="handleColorSelect"
      />
    </div>
  </div>
</template>

<script>
import ColorButton from "./ColorButton.vue";

export default {
  components: {
    ColorButton,
  },
  data() {
    return {
      colors: [
        { value: "rgba(255, 255, 255, 1)", name: "белый" },
        { value: "rgba(0, 0, 0, 1)", name: "чёрный" },
        { value: "rgba(249, 241, 220, 1)", name: "бежевый" },
      ],
      selectedColor: "белый",
    };
  },
  methods: {
    handleColorSelect(color) {
      this.selectedColor = color.name;
    },
  },
};
</script>

<style lang="scss" scoped>
@use "../../assets/styles/var.scss";
.product-color {
  margin-top: 36px;
  &__heading {
    font-size: 10px;
    font-weight: 400;
    line-height: 14px;
    color: var.$colorTextAdd;
    margin-bottom: 6px;
  }
  &__choose {
    display: flex;
    flex-direction: row;
    gap: 16px;
  }
}

@media (max-width: 766px) {
  .product-color {
    display: flex;
    flex-direction: column;
    align-items: flex-start;

    &__choose {
      display: flex;
      justify-content: center;
      gap: 10px;
      width: 100%;
    }
  }
}
</style>
