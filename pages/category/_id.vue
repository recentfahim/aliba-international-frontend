<template lang="html">
  <div class="ps-page--shop">
    <div class="martfury mt-5 mb-5" v-if="pageLoading">
      <div class="d-flex justify-content-center text-success">
        <div class="spinner-border" role="status">
          <span class="sr-only">Loading...</span>
        </div>
      </div>
    </div>
    <div class="container pt-4 pb-4" v-else>
      <div class="search-product-container">
        <SearchProductContainer :products="products"/>
      </div>
    </div>
  </div>
</template>

<script>
import Categoryproducts from '~/components/product/Categoryproducts.vue'
import axios from 'axios';
import SearchProductContainer from '~/components/search/SearchProductContainer';

export default {
  components: { Categoryproducts, SearchProductContainer },
  data(){
    return{
      category_id: this.$route.params.id,
      products: null,
      pageLoading: false,
    }
  },
  mounted() {
    this.pageLoading = true
    axios.get(process.env.baseURL + `category-product/` + this.category_id).then(response => {
      this.products = response.data.data
      this.pageLoading = false
    })
  }

}
</script>

<style lang="scss" scoped>
.ps-page--shop{
  background-color: $background-color;
}
.founded-product{
  background-color: #ffffff;
  border-radius: 5px;
  padding-left: 15px;
  padding-top: 10px;
  padding-bottom: 1px;
  margin-bottom: 5px;
}
</style>