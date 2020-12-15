<template>
    <div class="col-md-2">
      <div class="product-grid">
      <nuxt-link :to="`/product/${product.id}`">
        <div >
            <img class="product-image" :src="product.image">
        </div>
        <div class="product-price">
            BDT {{ this.product.price }}
        </div>
      </nuxt-link>
      </div>
    </div>
</template>

<script>
export default {
  name: "grid-product",
  props: ['product'],
}
</script>

<style scoped>
.product-grid{
    margin: 0 8px 16px;
    padding: 8px;
    background: #ffffff;
    border-radius: 10px;
    position: relative;
}
.product-price{
    display: block;
    color: #000;
    font-size: 14px;
    font-weight: 900;
    font-style: italic;
    font-family: OpenSans,Open Sans,Arial,Helvetica,sans-serif,SimSun,宋体;
}
.product-image{
    margin: 8px 0px;
    border-radius: 5px;
    height: 160px;
    width: 175px;
}
</style>