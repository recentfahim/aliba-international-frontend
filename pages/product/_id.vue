<template lang="html">
  <div class="martfury mt-5 mb-5" v-if="pageLoading">
    <div class="d-flex justify-content-center text-success">
      <div class="spinner-border" role="status">
        <span class="sr-only">Loading...</span>
      </div>
    </div>
  </div>
    <div class="martfury" v-else>
        <div class="ps-page--product">
            <div class="ps-container">
                <div class="ps-page__container">
                    <div class="ps-page__left">
                        <product-detail-fullwidth :product="product" v-if="product !== null" />
                    </div>
                    <div class="ps-page__right">
                        <product-widgets
                            v-if="product"
                        />
                    </div>
                </div>
                <div class="ps-page__container">
                    <!-- <div class="ps-page__left">
                        <!-- <secondary-part :product="product" v-if="product !== null" /> -->
                    <!-- </div> -->
                    <div>
                            <secondary-part
                                v-if="product"
                            />
                        
                    </div >
                    
                </div>       

                <div class="main">
                <div class="detail-container container flex">

                </div>
                </div>
                <customer-bought
                    v-if="collections !== null"
                    layout="fullwidth"
                    collection-slug="customer_bought"
                />
                <related-product
                    v-if="collections !== null"
                    layout="fullwidth"
                    collection-slug="shop-recommend-items"
                />
            </div>
        </div>
    </div>
</template>

<script>
import { mapState } from 'vuex';
import ProductDetailFullwidth from '~/components/elements/detail/ProductDetailFullwidth';
import BreadCrumb from '~/components/elements/BreadCrumb';
import CustomerBought from '~/components/partials/product/CustomerBought';
import RelatedProduct from '~/components/partials/product/RelatedProduct';
import ProductWidgets from '~/components/partials/product/ProductWidgets';
import LayoutProduct from '~/layouts/layout-product';
import Newsletters from '~/components/partials/commons/Newsletters';
import axios from 'axios';
import SecondaryPart from  '~/components/elements/detail/information/modules/SecondaryPart.vue';

export default {
    layout: 'layout-product',
    transition: 'zoom',
    components: {
        Newsletters,
        LayoutProduct,
        ProductWidgets,
        RelatedProduct,
        CustomerBought,
        BreadCrumb,
        ProductDetailFullwidth,
        SecondaryPart
    },

    computed: {
        ...mapState({
            collections: state => state.collection.collections,
        })
    },
    data() {
        return {
            productId: this.$route.params.id,
            breadCrumb: null,
            pageLoading: true,
            product: ''
        };
    },
    /*async created() {
        const queries = [
            'customer_bought',
            'shop-recommend-items',
            'widget_same_brand'
        ];
        setTimeout(
            function() {
                this.pageLoading = false;
            }.bind(this),
            2000
        );
        const collections = await this.$store.dispatch(
            'collection/getCollectionsBySlugs',
            queries
        );
        const product = await this.$store.dispatch(
            'product/getProductsById',
            this.productId
        );
        this.breadCrumb = [
            {
                text: 'Home',
                url: '/'
            },
            {
                text: 'Shop',
                url: '/shop'
            },
            {
                text: product.title
            }
        ];
    },*/
    mounted() {
        let product_id = this.$route.params.id
        axios.get(`${process.env.baseURL}single-product/${product_id}`).then((response) => {
            this.product = response.data.data
            this.pageLoading = false
        })
        this.$store.commit('app/setAppDrawer', false);
    }
};
</script>

<style lang="scss" scoped>

.product-store-banner[data-v-965ea09e][data-v-965ea09e] {
    overflow: hidden;
    max-width: 1355px;
    width: 100%;
    margin: 20px auto;
    border-radius: 70px;
    height: 60px;
}
.store-banner {
    height: 90px;
    text-align: center;
    line-height: 90px;
    background-color: #fff;
    background-position: 50%;
    background-size: cover;
    display: -ms-flexbox;
    display: flex;
    -ms-flex-align: center;
    align-items: center;
    -ms-flex-pack: center;
    justify-content: center;
}

// sidebar

// .detail-container {
//     max-width: 1200px;
//     width: 100%;
//     margin: 0 auto;
// }
// .flex {
//     display: -ms-flexbox;
//     display: flex;
// }

// .product-extend .product-extend-sidebar {
//     max-width: 200px;
//     width: 100%;
//     margin-right: 14px;
//     background-color: blue;
// }

// second container

.main{
    padding: 0;
    margin: 0;
    background-color: #f2f2f2;
}

</style>
