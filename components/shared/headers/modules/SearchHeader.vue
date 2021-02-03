<template lang="html">
    <form
        class="ps-form--quick-search"
        @submit.prevent="handleSubmit"
        v-click-outside="handleClickOutside"
    >
      <div class="input-group">
        <input type="text" class="form-control" placeholder="I'm looking for" v-model="searchText">
        <div class="input-group-append">
          <input type="file" class="form-control" ref="file" id="file" @change="handleFileUpload()">
        </div>
        <div class="input-group-append">
          <button class="btn btn-outline-secondary search-button-container" type="submit">
            <i class="fas fa-search search-button"></i>
          </button>
        </div>
      </div>
<!--        <div class="input-group">
            <input type="text" class="form-control" aria-label="Amount (to the nearest dollar)">
            <div class="input-group-append">
                <span class="input-group-text image-search-container">
                    <i class="fas fa-camera image-search"></i>
                  <input type="file" class="search-file-input">
                </span>
                <button class="input-group-text search-button-container">
                    <i class="fas fa-search search-button"></i>
                </button>
            </div>
        </div>-->
    </form>
</template>

<script>
import { mapState } from 'vuex';
import ProductResult from '~/components/elements/product/ProductResult';
import axios from 'axios';

export default {
    name: 'SearchHeader',
    components: { ProductResult },
    computed: {
        ...mapState({
            searchResults: state => state.product.searchResults
        })
    },
    data() {
        return {
            exampleCategories: [
                'All',
                'Babies & Moms',
                'Books & Office',
                'Cars & Motocycles',
                'Clothing & Apparel',
                ' Accessories',
                'Bags',
                'Kid’s Fashion',
                'Mens',
                'Shoes',
                'Sunglasses',
                'Womens',
                'Computers & Technologies',
                'Desktop PC',
                'Laptop',
                'Smartphones',
                'Consumer Electrics',
                'Air Conditioners',
                'Accessories',
                'Type Hanging Cell',
                'Audios & Theaters',
                'Headphone',
                'Home Theater System',
                'Speakers',
                'Car Electronics',
                'Audio & Video',
                'Car Security',
                'Radar Detector',
                'Vehicle GPS',
                'Office Electronics',
                'Printers',
                'Projectors',
                'Scanners',
                'Store & Business',
                'Refrigerators',
                'TV Televisions',
                '4K Ultra HD TVs',
                'LED TVs',
                'OLED TVs',
                'Washing Machines',
                'Type Drying Clothes',
                'Type Horizontal',
                'Type Vertical',
                'Garden & Kitchen',
                'Cookware',
                'Decoration',
                'Furniture',
                'Garden Tools',
                'Home Improvement',
                'Powers And Hand Tools',
                'Utensil & Gadget',
                'Health & Beauty',
                'Equipments',
                'Hair Care',
                'Perfumer',
                'Wine Cabinets'
            ],
            isSearching: false,
            isLoading: false,
            searchText: '',
            searchImage: null
        };
    },
    methods: {
        async handleSearchProduct(e) {
            if (e.target.value !== '') {
                this.isSearching = true;
                const query = {
                    title_contains: e.target.value
                };
                this.isLoading = true;
                const result = await this.$store.dispatch(
                    'product/getProductByKeyword',
                    query
                );
                if (result) {
                    setTimeout(
                        function() {
                            this.isLoading = false;
                        }.bind(this),
                        500
                    );
                }
            } else {
                this.isSearching = false;
            }
        },
        handleClickOutside() {
            this.searchText = '';
            this.isSearching = false;
            this.isLoading = false;
        },
      handleFileUpload(event){
        this.searchImage = this.$refs.file.files[0];
        const formData = new FormData()
        formData.append('search_image', this.searchImage)
        axios.post(process.env.baseURL + `get-search-image-url`, formData).then((response) =>{
          this.$router.push({
            path: 'search',
            query: { keyword: response.data.image_url },
          })
        })
      },

      handleSubmit() {
        console.log(this.$route.path)
        if (this.searchText !== null || this.searchText !== '') {
          this.$router.push({
            path: 'search',
            query: { keyword: this.searchText },
          })
          }

      }
    }
};
</script>

<style lang="scss" scoped>
.ps-form--quick-search {
    .ps-form__input {
        position: relative;
        width: 100%;
        .v-progress-circular {
            @include vertical-align();
            right: 10px;
            z-index: 20;
        }
        border: 1px solid red;
    }
}
.input-group{
    border: 2px solid #ff4747;
    line-height: 18px;
    font-size: 13px;
    border-radius: 5px;
}
.search-button-container{
    margin-right: -2px;
    height: 42px;
    background-color: #ff4747;
    border-radius: 0 4px 4px 0;
    cursor: pointer;
    color: #fff;
    border: none;
}
.search-button{
    font-size: 17px;
    margin-left: 7px;
}
.image-search{
    font-size: 17px;
    vertical-align: middle;
    color: #ffffff;
    padding: 7px;
    background: #ff4747;
    border-radius: 50% !important;
    cursor: pointer;
}
.image-search-container{
    background-color: #ffffff;
}

.search-file-input::-webkit-file-upload-button {
  visibility: hidden;
}
.search-file-input::before {
  content: 'Select some files';
  display: inline-block;
  background: linear-gradient(top, #f9f9f9, #e3e3e3);
  border: 1px solid #999;
  border-radius: 3px;
  padding: 5px 8px;
  outline: none;
  white-space: nowrap;
  -webkit-user-select: none;
  cursor: pointer;
  text-shadow: 1px 1px #fff;
  font-weight: 700;
  font-size: 10pt;
}
.search-file-input:hover::before {
  border-color: black;
}
.search-file-input:active::before {
  background: -webkit-linear-gradient(top, #e3e3e3, #f9f9f9);
}
</style>
