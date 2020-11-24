<template>
    <div>
        <div class="container">
            <div class="card">
                <div class="card-header">
                    <div>Recommended for you</div>
                </div>
                <div class="card-body">
                    <div class="row">
                        <div v-for="product in products"
                             class="col-xl-2 col-lg-2 col-md-3 col-sm-4 col-6"
                             :key="product.id">
                            <product-default :product="product" />
                        </div>
                    </div>
                </div>
            </div>

        </div>
    </div>
</template>

<script>
import { mapState } from 'vuex';
import axios from 'axios';
import ProductDefault from '@/components/elements/product/ProductDefault';

export default {
name: "ProductList.vue",
    components: {
        ProductDefault
    },
    data(){
        return {
            products: [],
            baseDomain: 'http://45.76.97.89:3000',
        }

    },
    mounted() {
        axios.get(`${process.env.baseURL}product`).then((response) => {
            this.products = response.data.data
        })
    }
}
</script>

<style scoped>

</style>