<template>
  <div class="product-color">
    <h4 class="product-color__heading">Цвет: {{ selectedColor }}</h4>
    <div class="product-color__choose">
      <ColorButton
        v-for="color in colors"
        :key="color.id"
        :color="color"
        :selectedColorId="selectedColorId"
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
      selectedColorId: "color-white",
      colors: [
        { id: "color-white", value: "rgba(255, 255, 255, 1)", name: "белый" },
        { id: "color-black", value: "rgba(0, 0, 0, 1)", name: "чёрный" },
        { id: "color-beige", value: "rgba(249, 241, 220, 1)", name: "бежевый" },
      ],
      selectedColor: "белый",
    };
  },
  methods: {
    handleColorSelect(color) {
      this.selectedColorId = color.id;
      this.selectedColor = color.name;
      this.$emit("select", color);
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
      justify-content: flex-start;
      gap: 10px;
      width: 100%;
    }
  }
}
</style>
