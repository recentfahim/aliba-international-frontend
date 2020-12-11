<template>
   <main id="ProductMain">
       <div class="container">
            
        </div>
        <div class="container pt-5">
           <ProductMain></ProductMain>
        </div>
        <div class="container mt-5">
            
        </div>
        <div class="container mt-5">
    
        </div>
        <div class="container mt-5">
        
        </div>
        <div class="container mt-5">
        
        </div>
        
        <div class="container mt-5">
           
        </div>    
    </main>
</template>

<script>
import { mapState } from 'vuex';
import ProductGridView from '~/components/product/product-grid-view';
import ProductMain from '~/components/ProductPage/ProductMain';

export default {
    components: {
    ProductGridView,
    ProductMain
    },
    transition: 'zoom',
    layout: 'layout-default',
};
</script>

<style scoped>
#ProductMain{
    background-color: #f2f2f2;
}

</style>