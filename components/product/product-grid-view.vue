<template>
    <div class="row text-center" v-if="pageLoading">
        <div class="d-flex justify-content-center text-success">
          <div class="spinner-border" role="status">
            <span class="sr-only">Loading...</span>
          </div>
        </div>
    </div>
    <div class="row" v-else>
        <grid-product v-for="(product, index) in products" :key="index" :product="product"></grid-product>
    </div>
</template>

<script>
import GridProduct from '~/components/product/grid-product'
import axios from 'axios';
export default {
  name: "product-grid-view",
  components: { GridProduct },

  data() {
    return{
      products: null,
      pageLoading: true
    }
  },

  created() {
    axios.get(process.env.baseURL + `product`).then((response) => {
      this.products = response.data.data
      this.pageLoading = false
    })
  }


}
</script>

<style scoped>

</style>