<template>
    <div class="product-grid">
        <div >
            <img class="product-image" src="https://ae01.alicdn.com/kf/H5a564bdcec0346ae888c5cb5389ad76dO.jpg_350x350xz.jpg">
<!--            <img class="product-image" src="https://ae01.alicdn.com/kf/H73f804fdf9d4403182ec701c146d7628R.jpg_200x200.jpg">-->
        </div>
        <div class="product-price">
            BDT 305.68
        </div>
    </div>
</template>

<script>
export default {
name: "grid-product"
}
</script>

<style scoped>
.product-grid{
    width: 15.367%;
    margin: 0 8px 16px;
    padding: 8px;
    background: #ffffff;
    height: 200px;
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
    height: 160px;
    width: 175px;
}
</style>