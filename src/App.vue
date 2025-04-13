<template>
  <ProductPage />
</template>

<script>
import ProductPage from "./ProductPage";

export default {
  name: "App",
  components: {
    ProductPage,
  },
};
</script>

<style lang="scss">

@font-face {
  font-family: Helvetica;
  src: url(/fonts/helvetica_regular.otf);
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Helvetica;
}


a {
  text-decoration: none;
}
</style>
