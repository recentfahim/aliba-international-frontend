<template>
    <div class="product">
        <div class="product-image">
            <img src="https://ae01.alicdn.com/kf/Hb9fa59a7e5864107bb1fc6db9cb510f3L.jpg_120x120Q90.jpg" alt="gd">
        </div>
        <div class="product-price">
            BDT 421
        </div>
    </div>
</template>

<script>
export default {
name: "TopRankingProduct"
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