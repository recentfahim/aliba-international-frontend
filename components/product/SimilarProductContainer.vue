<template>
  <div class="row m-0">
    <SimilarProduct v-for="(item, index) in similar_products" :key="index" :item="item"/>
  </div>
</template>

<script>
import SimilarProduct from '~/components/product/SimilarProduct';
export default {
name: "SimilarProductContainer",
  props: ['similar_products'],
  components: { SimilarProduct }
}
</script>

<style scoped>

</style>