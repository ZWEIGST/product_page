<template>
  <ProductPage/>
</template>

<script>
import ProductPage from './components/ProductPage.vue'

export default {
  name: 'App',
  components: {
    ProductPage,
  }
}
</script>

<style lang="scss">
 $text-color--h2: rgba(51, 51, 51, 1);
 $text-color--h3: rgba(79, 79, 79, 1);

@mixins description-text {
    color: rgba(51, 51, 51, 1);
    font-family: Helvetica;
    font-size: 12px;
    font-weight: 400;
    line-height: 16px;
    text-decoration-skip-ink: none;
}
@media (min-width: 319px) and (max-width: 766px) {

}
</style>
