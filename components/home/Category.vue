<template>
    <div class="category-container" v-if="pageLoading">
      <div class="d-flex justify-content-center text-success">
        <div class="spinner-border" role="status">
          <span class="sr-only">Loading...</span>
        </div>
      </div>
    </div>
    <div class="category-container" v-else>
        <ul class="category-list">
            <li class="category-item" v-for="category in categories">
              <nuxt-link :to="`/category/${category.Id}`">
                <div class="d-flex">
                    <div class="category-item-text ml-2">
                        {{ category.Name }}
                    </div>
                </div>
              </nuxt-link>
              <div class="subcategory-tooltip">{{category.Name}}</div>
            </li>
        </ul>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'Category',

    data() {
        return{
            categories: [],
            sub_categories: [],
            pageLoading: true
        }
    },

    methods: {
      getSubCategory(data){
          axios.get(process.env.baseURL + `sub-category/`+ data).then((response) => {
              this.sub_categories = response.data.data
          })
      }
    },

    created() {
        axios.get(process.env.baseURL + `category`).then((response) => {
            this.categories = response.data.data
            this.pageLoading = false
        })
    }
};
</script>

<style scoped>
.category-list {
    list-style: none;
}

.category-item {
    line-height: 35px;
}
.category-item-icon{
    width: 30px;
    text-align: center;
}

.category-item:hover{
    border-bottom: 1px solid #eaeaea;
    border-left: 2px solid #e2e2e2;
    color: #e62e04;
}
.category-item-text:hover{
    font-weight: 600;
}

.category-container {
    background-color: #ffffff;
    margin-top: -21px;
}
.category-item .subcategory-tooltip {
  visibility: hidden;
  width: 800px;
  height: 500px;
  background-color: #ffffff;
  color: #000000;
  text-align: center;
  padding: 5px 0;
  border-radius: 6px;

  /* Position the tooltip text - see examples below! */
  position: absolute;
  z-index: 1;
  top: -5px;
  left: 96%;
}

/* Show the tooltip text when you mouse over the tooltip container */
.category-item:hover .subcategory-tooltip {
  visibility: visible;
}
</style>