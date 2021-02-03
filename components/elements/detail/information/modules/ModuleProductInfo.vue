<template lang="html">
  <div>
    <h1 class="product-title-text" v-html="product.Title"></h1>
    <div class="ps-product__meta mt-4">
      <div class="ps-product__rating">
        <div v-for="product_meta in product.FeaturedValues" v-if="product_meta.Name === 'TotalSales'">
          <span class="ml-0">Total Sales {{ product_meta.Value}}</span>
        </div>
      </div>
    </div>
   <h4 v-if="product.IsSellAllowed" class="ps-product-price">
      BDT {{ product.Price.ConvertedPriceWithoutSign }}
    </h4>
  </div>

</template>

<script>
import Rating from '~/components/elements/Rating';
export default {
  name: 'ModuleProductInfo',
  props: ['product'],
  components: { Rating },

};
</script>

<style lang="scss" scoped>
.ps-product__rating span{
  margin-left: 0;
}
.ps-product-price{
  color: #000000;
  font-size: 24px;
  font-weight: 700;
  font-family: Open Sans,sans-serif;
}

.product-title-text {
  font-size: 20px;
  line-height: 25px;
  margin: 0;
  width: -webkit-fit-content;
  width: -moz-fit-content;
  width: fit-content;
}
</style>
