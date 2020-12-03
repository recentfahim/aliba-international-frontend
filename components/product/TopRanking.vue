<template>
    <v-row>
        <v-col md="12" class="top-ranking-sale">
            <div class="title-container ">
                <div class="title-info">
                    <div class="top-ranking-icon">
                        <i class="fas fa-star"></i>
                    </div>
                    <h3>Top Ranking</h3>
                    <span class="view-more">View more</span>
                </div>

            </div>
            <div class="product-container">
                <top-ranking-product-container></top-ranking-product-container>
            </div>
        </v-col>
    </v-row>
</template>

<script>
import FlashSaleProduct from '~/components/product/flash-sale-product';
import TopRankingProductContainer from '~/components/product/TopRankingProductContainer';

export default {
    name: "TopRanking",
    components: {
        FlashSaleProduct,
        TopRankingProductContainer
    }
}
</script>

<style scoped>
.top-ranking-sale{
    height: 300px;
    background-color: #ffffff;
    border-radius: 10px;
}
.view-more{
    float: right;
    line-height: 24px;
    color: #999;
    font-size: 12px;
    white-space: nowrap;
    position: absolute;
    right: 0px;
}

.title-container {
    padding: 16px 5px 12px;
    overflow: hidden;
}
.top-ranking-icon{
    height: 30px;
    width: 30px;
    border-radius: 50%;
    background-color: #bd2e06;
    color: #ffffff;
}
.top-ranking-icon i{
    padding: 5px 6px;
    font-size: 18px;
}
.title-info{
    display: flex;
    position: relative;
}
.title-info h3{
    color: #000;
    margin: 6px 0px 0 10px;
    padding: 0 2px;
    line-height: 20px;
    font-size: 16px;
    font-weight: 900;
    font-family: OpenSans,Open Sans,Arial,Helvetica,sans-serif,SimSun,宋体;
}
</style>