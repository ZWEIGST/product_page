<template>
  <ProductPage />
</template>

<script>
import ProductPage from "./components/ProductPage.vue";

export default {
  name: "App",
  components: {
    ProductPage,
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
a {
  text-decoration: none;
}
body {
  @font-face {
    font-family: Helvetica;
    src: url(/fonts/helvetica_regular.otf);
  }
}
</style>
