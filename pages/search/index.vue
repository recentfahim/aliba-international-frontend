<template lang="html">
    <div class="ps-page--shop">
        <div class="container pt-4 pb-4">
          <div class="founded-product">
            <div>
              <h5>85 Products found</h5>
            </div>
          </div>
          <div class="search-product-container">
            <SearchProductContainer/>
          </div>
        </div>
    </div>
</template>

<script>
import { mapState } from 'vuex';
import SearchProductContainer from '~/components/search/SearchProductContainer';
import axios from 'axios';

export default {
    transition() {
        return 'fadeIn';
    },
    data() {
      return {
        search_keyword: this.$route.query.keyword
      };
    },
    components: {
      SearchProductContainer,
    },

    computed: {
        keyword() {
            return this.$route.query.keyword;
        }
    },



    async created() {
      var search_key = this.search_keyword
      if(search_key.endsWith('.png') || search_key.endsWith('.jpg') || search_key.endsWith('.jpeg')){
        axios.get(process.env.baseURL + `search-by-image?search_key=` + this.search_keyword).then((response) => {
          console.log(response.data)
        })
      }
        else {
        axios.get(process.env.baseURL + 'search-by-text?search_key=' + this.search_keyword).then((response) => {
          console.log(response.data)
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
