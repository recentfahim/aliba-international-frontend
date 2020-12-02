<template>
    <v-col md="3">
        <div class="product-grid">
            <div >
                <img class="product-image" src="https://ae01.alicdn.com/kf/H5a564bdcec0346ae888c5cb5389ad76dO.jpg_350x350xz.jpg">
                <!--            <img class="product-image" src="https://ae01.alicdn.com/kf/H73f804fdf9d4403182ec701c146d7628R.jpg_200x200.jpg">-->
            </div>
            <div class="product-price">
                <span class="current-price">
                    BDT 305.68
                </span>
                <span class="discount">
                    20% off
                </span>
            </div>
        </div>
    </v-col>
</template>

<script>
export default {
name: "flash-sale-product"
}
</script>

<style scoped>
.product-grid{
    margin: 0 8px 16px;
    padding: 8px;
    background: #f3f3f3;
    height: 230px;
    border-radius: 10px;
    position: relative;
}
.product-price{
    position: absolute;
    bottom: 8px;
    left: 10px;
    line-height: 18px;
    color: #000;
    font-size: 14px;
    font-weight: 900;
    font-style: italic;
    font-family: OpenSans,Open Sans,Arial,Helvetica,sans-serif,SimSun,宋体;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.product-image{
    margin: 0;
    border-radius: 5px;
    height: 190px;
    width: 250px;
}
.discount{
    float: right;
    font-size: 12px;
    line-height: 12px;
    padding: 2px 10px;
    background: #ffecec;
    color: #ff4747;
    font-family: OpenSans-Semibold,Open Sans,Arial,Helvetica,sans-serif,SimSun,宋体;
    letter-spacing: 0;
    text-align: center;
    font-style: normal;
    margin-left: 115px;
}
.current-price {
    float: left;
    display: block;
    line-height: 18px;
    color: #000;
    font-size: 14px;
    font-weight: 900;
    font-style: italic;
    font-family: OpenSans,Open Sans,Arial,Helvetica,sans-serif,SimSun,宋体;
}
</style>