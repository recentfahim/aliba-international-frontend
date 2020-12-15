<template lang="html">
  <div>
    <h1>{{ product.Title }}</h1>
    <div class="ps-product__meta">
      <div class="ps-product__rating">
        <div v-for="product_meta in product.FeaturedValues" v-if="product_meta.Name === 'TotalSales'">
          <span> Total Sales {{ product_meta.Value}}</span>
        </div>
      </div>
    </div>
   <h4 v-if="product.IsSellAllowed" class="ps-product__price sale">
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
</style>
