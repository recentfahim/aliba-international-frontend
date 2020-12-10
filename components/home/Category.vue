<template>
    <div class="category-container">
        <ul class="category-list">
            <li class="category-item" v-for="category in categories" @mouseenter="getSubCategory(category.Id)">
                <div class="d-flex">
                    <div class="category-item-text ml-2">
                        {{ category.Name }}
                    </div>
                </div>
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
            sub_categories: []
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
</style>