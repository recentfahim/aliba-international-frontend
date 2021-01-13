<template lang="html">
  <div class="martfury mt-5 mb-5" v-if="pageLoading">
    <div class="d-flex justify-content-center text-success">
      <div class="spinner-border" role="status">
        <span class="sr-only">Loading...</span>
      </div>
    </div>
  </div>
  <div class="martfury" v-else>
    <div class="ps-page--product pb-lg-5">
        <div class="ps-container">
            <div class="ps-page__container">
                <div class="ps-page__left">
                    <product-detail-fullwidth :product="product" v-if="product !== null" />
                </div>
                <div class="ps-page__right">
                    <product-widgets
                        v-if="product" :recommended_item="recommend_for_you"
                    />
                </div>
            </div>
        </div>
    </div>
    <div class="similar-product-description-container">
      <div class="similar-product">
        <secondary-part v-if="product" :similar_products="similar_product"/>
      </div>
      <div class="product-description">
        <ProductDescription :description="product_description"/>
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
import axios from 'axios';
import SecondaryPart from  '~/components/elements/detail/information/modules/SecondaryPart.vue';
import ProductDescription from '~/components/product/ProductDescription';

export default {
    layout: 'layout-product',
    transition: 'zoom',
    components: {
      ProductDescription,
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
            product: '',
            product_description: null,
            recommend_for_you: null,
            similar_product: null
        };
    },
    mounted() {
        let product_id = this.$route.params.id
        axios.get(`${process.env.baseURL}single-product/${product_id}`).then((response) => {
            this.product = response.data.data
            this.product_description = response.data.description
            this.recommend_for_you = response.data.related_product.slice(0, 3);
            this.similar_product = response.data.related_product.slice(3, 9);
            this.pageLoading = false
        })
        this.$store.commit('app/setAppDrawer', false);
    }
};
</script>

<style lang="scss" scoped>

.product-store-banner {
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
.similar-product-description-container{
  padding: 25px;
  margin: 0;
  background-color: #f2f2f2;
}
.similar-product{
  background-color: #ffffff;
  border-radius: 5px;
  margin-bottom: 15px;
}
</style>
