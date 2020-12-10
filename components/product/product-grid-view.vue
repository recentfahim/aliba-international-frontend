<template>
    <div class="row">
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
      products: null
    }
  },

  created() {
    axios.get(process.env.baseURL + `product`).then((response) => {
      this.products = response.data.data
    })
  }


}
</script>

<style scoped>

</style>