<template>
  <div class="col-md-2 col-sm-3 col-6">
    <div class="product-grid">
      <nuxt-link :to="`/product/${item.id}`">
        <div class="product-image-container">
          <img class="product-image" :src="item.image">
        </div>
        <div class="product-price">
          BDT {{ item.price }}
        </div>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SimilarProduct',
  props: ['item']
};
</script>

<style scoped>
.product-image-container{
  border: 1px solid #f2f2f2;
}
.product-grid{
  margin: 15px 0;
}
.product-price{
  text-align: center;
  margin-top: 5px;
  color: #000;
  font-size: 14px;
  font-weight: 900;
  font-style: italic;
  font-family: OpenSans,Open Sans,Arial,Helvetica,sans-serif,SimSun,宋体;
}
.product-image{
  padding: 10px;
  height: 190px;
}
</style>