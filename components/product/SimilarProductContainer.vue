<template>
  <div class="row m-0">
    <SimilarProduct/>
    <SimilarProduct/>
    <SimilarProduct/>
    <SimilarProduct/>
    <SimilarProduct/>
    <SimilarProduct/>
  </div>
</template>

<script>
import SimilarProduct from '~/components/product/SimilarProduct';
export default {
name: "SimilarProductContainer",
  components: { SimilarProduct }
}
</script>

<style scoped>

</style>