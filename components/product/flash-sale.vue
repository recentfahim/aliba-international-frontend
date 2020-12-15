<template>
    <v-row>
        <v-col md="12" class="flash-sale">
            <div class="title-container ">
                <div class="title-info">
                    <div class="flash-sale-icon">
                        <i class="fas fa-bolt"></i>
                    </div>
                    <h3>Flash Deals</h3>
                    <span class="view-more">View more</span>
                </div>

            </div>
            <div v-if="pageLoading" class="mt-5 mb-5">
              <div class="d-flex justify-content-center text-success">
                <div class="spinner-border" role="status">
                  <span class="sr-only">Loading...</span>
                </div>
              </div>
            </div>
            <div class="product-container" v-else>
                <v-row>
                    <flash-sale-product v-for="(product, index) in flash_sale_products" :product="product" :key="index"></flash-sale-product>
                </v-row>
            </div>
        </v-col>
    </v-row>
</template>

<script>
import FlashSaleProduct from '~/components/product/flash-sale-product'
import axios from 'axios';

export default {
    name: 'flash-sale',
    components: {
        FlashSaleProduct
    },

    data(){
      return{
        flash_sale_products: null,
        pageLoading: true
      }
    },

    created() {
      axios.get(process.env.baseURL + `home-product`).then((response) => {
          this.flash_sale_products = response.data.data
          this.pageLoading = false
      })
    }
};
</script>

<style scoped>
.flash-sale{
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
.flash-sale-icon{
    height: 30px;
    width: 30px;
    border-radius: 50%;
    background-color: #fc5a2c;
    color: #ffffff;
}
.flash-sale-icon i{
    padding: 7px 10px;
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