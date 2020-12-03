<template>
    <v-row class="product-container">
        <v-col md="4" class="ranking-list">
            <v-row>
                <v-col md="8">
                    Cost-effective $10 Goods - Flashlights & Torches
                </v-col>
                <v-col md="4">
                    Top Picks
                </v-col>
            </v-row>
            <v-row>
                <v-col md="4">
                    <top-ranking-product></top-ranking-product>
                </v-col>
                <v-col md="4">
                    <top-ranking-product></top-ranking-product>
                </v-col>
                <v-col md="4">
                    <top-ranking-product></top-ranking-product>
                </v-col>
            </v-row>
        </v-col>
        <v-col md="4" class="ranking-list">
            <v-row>
                <v-col md="8">
                    Cost-effective $10 Goods - Flashlights & Torches
                </v-col>
                <v-col md="4">
                    Top Picks
                </v-col>
            </v-row>
            <v-row>
                <v-col md="4">
                    <top-ranking-product></top-ranking-product>
                </v-col>
                <v-col md="4">
                    <top-ranking-product></top-ranking-product>
                </v-col>
                <v-col md="4">
                    <top-ranking-product></top-ranking-product>
                </v-col>
            </v-row>
        </v-col>
        <v-col md="4" class="ranking-list">
            <v-row>
                <v-col md="8">
                    Cost-effective $10 Goods - Flashlights & Torches
                </v-col>
                <v-col md="4">
                    Top Picks
                </v-col>
            </v-row>
            <v-row>
                <v-col md="4">
                    <top-ranking-product></top-ranking-product>
                </v-col>
                <v-col md="4">
                    <top-ranking-product></top-ranking-product>
                </v-col>
                <v-col md="4">
                    <top-ranking-product></top-ranking-product>
                </v-col>
            </v-row>
        </v-col>
    </v-row>
</template>

<script>
import TopRankingProduct from '~/components/product/TopRankingProduct';

export default {
    name: 'TopRankingProductContainer',
    components: {
        TopRankingProduct
    }
};
</script>

<style scoped>
.ranking-list{
    background-color: rgba(0,0,0,.04);
    border-radius: 5px;
}
.product-container{

}
</style>