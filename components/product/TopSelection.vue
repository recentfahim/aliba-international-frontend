<template>
    <v-row>
        <v-col md="6" class="pl-0">
            <div class="top-selection">
                <div class="title-container">
                    <div class="title-info">
                        <div class="top-ranking-icon">
                            <i class="fas fa-star"></i>
                        </div>
                        <h3>Top Selection</h3>
                        <span class="view-more">View more</span>
                    </div>
                </div>
                <v-row>
                    <v-col md="3">
                        <ProductGrid></ProductGrid>
                    </v-col>
                    <v-col md="3">
                        <ProductGrid></ProductGrid>
                    </v-col>
                    <v-col md="3">
                        <ProductGrid></ProductGrid>
                    </v-col>
                    <v-col md="3">
                        <ProductGrid></ProductGrid>
                    </v-col>
                </v-row>


            </div>

        </v-col>
        <v-col md="6" class="pr-0">
            <div class="top-selection">
                <div class="title-container ">
                    <div class="title-info">
                        <div class="top-ranking-icon">
                            <i class="fas fa-star"></i>
                        </div>
                        <h3>New Arrivals</h3>
                        <span class="view-more">View more</span>
                    </div>
                </div>
            </div>
        </v-col>
    </v-row>
</template>

<script>
import ProductGrid from '~/components/product/grid-product';

export default {
    name: "TopSelection",
    components: {
        ProductGrid
    }
}
</script>

<style scoped>
.top-selection{
    height: 250px;
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