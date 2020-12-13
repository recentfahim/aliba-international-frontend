<template>
    <div class="product">
        <div class="product-image">
            <img :src="product.image" alt="">
        </div>
        <div class="product-price">
            BDT {{ product.price }}
        </div>
    </div>
</template>

<script>
export default {
  name: "TopRankingProduct",
  props: ['product']
}
</script>

<style scoped>
.product{
    position: relative;
}
.product-price{
    position: absolute;
    bottom: 0;
    background-color: hsla(0,0%,100%,.75);
    width: 100%;
    text-align: center;
}
</style>