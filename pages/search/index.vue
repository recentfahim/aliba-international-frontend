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
          <div class="founded-product">
            <div v-if="search_text">
              <span>Looking for <strong>"{{search_text}}"</strong> ({{product_found}} Results)</span>
            </div>
          </div>
          <div class="search-product-container">
            <SearchProductContainer :products="products"/>
          </div>
        </div>
    </div>
</template>

<script>
import { mapState } from 'vuex';
import SearchProductContainer from '~/components/search/SearchProductContainer';
import axios from 'axios';
import SecondaryPart from '~/components/elements/detail/information/modules/SecondaryPart';

export default {
    transition() {
        return 'fadeIn';
    },
    data() {
      return {
        search_keyword: this.$route.query.keyword,
        products: null,
        product_found: null,
        search_text: null,
        pageLoading: false

      };
    },
    components: {
      SecondaryPart,
      SearchProductContainer,
    },

    async created() {
      var search_key = this.search_keyword
      this.pageLoading = true
      if(search_key.endsWith('.png') || search_key.endsWith('.jpg') || search_key.endsWith('.jpeg')){
        axios.get(process.env.baseURL + `search-by-image?search_key=` + this.search_keyword).then((response) => {
          this.products = response.data.search_products
          this.product_found = response.data.search_products.length
          this.pageLoading = false
        })
      }
      else {
        axios.get(process.env.baseURL + 'search-by-text?search_key=' + this.search_keyword).then((response) => {
          this.products = response.data.search_products
          this.product_found = response.data.search_products.length
          this.search_text = this.search_keyword
          this.pageLoading = false
        })
      }
    }

};
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
