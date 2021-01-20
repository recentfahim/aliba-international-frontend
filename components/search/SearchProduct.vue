<template>
<div class="product-grid">
  <div>
    <div class="product-image">
      <img :src="product.image">
    </div>
    <div class="product-des-container">
      <div class="product-title">
        <p>{{product.title}}</p>
      </div>
      <div class="product-price">
        <p>BDT {{ Math.round(product.price)}}</p>
      </div>
      <div class="product-sold">
        <p>302 sold</p>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
name: "SearchProduct",
  props: ['product']
}
</script>

<style scoped>
.product-grid{
  background-color: #ffffff;
  margin-top: 10px;
  border-radius: 8px;
}
.product-des-container{
  margin: 5px 10px 5px 10px;
  padding-bottom: 1px;
}
.product-title{
  display: -webkit-box;
  -webkit-line-clamp: 1;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
.product-title p{
  color: #333;
  vertical-align: middle;
  width: 100%;
  height: 16px;
  margin-bottom: 2px;
  line-height: 14px;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
.product-price p{
  margin-top: 3px;
  font-size: 16px;
  line-height: 22px;
  font-weight: 700;
  color: #000;
  font-family: Open Sans,Arial,Helvetica,sans-serif,Heiti;
}
.product-sold{
  margin-top: -15px;
}
.product-image img{
  width: 180px;
  height: 180px;
}
</style>