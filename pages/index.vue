<template lang="html">
    <main id="homepage-1">
        <div class="container pt-5">
            <CatSliderSign></CatSliderSign>
        </div>
        <div class="container mt-5">
            <flash-sale></flash-sale>
        </div>
        <div class="container mt-5">
            <top-ranking></top-ranking>
        </div>
        <div class="container mt-5">
            <TopSelection></TopSelection>
        </div>
        <div class="container mt-5">
            <FeaturedBrands></FeaturedBrands>
        </div>
         <!-- <div class="container mt-5">
            <StoresYouWillLove></StoresYouWillLove>
        </div> -->
        <div class="container mt-5">
            <h3>More To Love</h3>
            <product-grid-view></product-grid-view>
        </div>    
    </main>
</template>
<script>
import { mapState } from 'vuex';
import ProductList from '~/components/partials/homepage/default/ProductList';
import ProductGridView from '~/components/product/product-grid-view';
import FlashSale from '~/components/product/flash-sale';
import TopRanking from '~/components/product/TopRanking';
import TopSelection from '~/components/product/TopSelection';
import CatSliderSign from '~/components/home/CatSliderSign';
import FeaturedBrands from '~/components/product/FeaturedBrands';
// import StoresYouWillLove from '~/components/product/StoresYouWillLove';

export default {
    components: {
        ProductList,
        ProductGridView,
        FlashSale,
        TopRanking,
        TopSelection,
        CatSliderSign,
        FeaturedBrands
    },
    transition: 'zoom',
    layout: 'layout-default',
};
</script>
<style scoped>
#homepage-1{
    background-color: #f2f2f2;
}
</style>