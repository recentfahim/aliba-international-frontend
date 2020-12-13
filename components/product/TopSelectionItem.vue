<template>
    <div class="product-grid">
        <div >
            <img class="product-image" :src="product.image">
            <!--            <img class="product-image" src="https://ae01.alicdn.com/kf/H73f804fdf9d4403182ec701c146d7628R.jpg_200x200.jpg">-->
        </div>
        <div class="product-price">
            BDT {{ product.price }}
        </div>
        <div class="mt-6">
            <span class="badge badge-pill badge-info  badge-size"> <i class="far fa-smile"></i> 218</span>
        </div>
    </div>
</template>

<script>
export default {
  name: "TopSelectionItem",
  props: ['product']
}
</script>

<style scoped>
.product-grid{
    width: 100%;
    padding: 8px;
    background: #ffffff;
    height: 175px;
    border-radius: 10px;
    position: relative;
}
.product-price{
    position: absolute;
    bottom: 8px;
    left: 10px;
    display: block;
    line-height: 18px;
    color: #000;
    font-size: 14px;
    font-weight: 900;
    font-style: italic;
    font-family: OpenSans,Open Sans,Arial,Helvetica,sans-serif,SimSun,宋体;
}
.product-image{
    margin: 8px 0px;
    border-radius: 5px;
    height: 125px;
    width: 170px;
}
.badge-size{
    font-weight: 100;
    font-size: 15px;
}
</style>