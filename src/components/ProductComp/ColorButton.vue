<template>
  <button
    class="product-color__button"
    :style="{ backgroundColor: color.value }"
    :class="{
      'product-color__button--white': isWhite,
      'product-color__button--active': isActive,
    }"
    @click="handleClick"
  ></button>
</template>

<script>
export default {
  props: {
    color: {
      type: Object,
      required: true,
    },
    selectedColorId: {
      type: String,
      default: null,
    },
  },
  computed: {
    isWhite() {
      return this.color.value.toLowerCase() === "rgba(255, 255, 255, 1)";
    },
    isActive() {
      return this.color.id === this.selectedColorId;
    },
  },
  methods: {
    handleClick() {
      this.$emit("select", this.color);
    },
  },
};
</script>

<style lang="scss" scoped>
@use "../../assets/styles/var.scss";
.product-color {
  &__button {
    width: 28px;
    height: 27px;
    position: relative;
    border: none;
    &:hover {
      border: 1px solid rgba(189, 189, 189, 1);
    }
    &::after {
      content: "";
      position: absolute;
      bottom: -3px;
      left: 50%;
      transform: translateX(-50%);
      width: 34px;
      height: 1px;
      background-color: var.$colorTextAdd;
      opacity: 0;
      transition: opacity 0.3s ease;
    }
    &--active::after {
      opacity: 1;
    }
    &--white {
      border: 1px solid rgba(189, 189, 189, 1);
    }
  }
}
</style>
