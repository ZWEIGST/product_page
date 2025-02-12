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

@font-face {
    font-family: Helvetica;
    src: url(/fonts/helvetica_regular.otf);
   }
h {
    font-family: Helvetica;
}
a {
    text-decoration: none;
}
</style>