<template>
  <div>
      <v-tabs v-model="tab">
        <v-tabs-slider color="black"></v-tabs-slider>
        <v-tab class="description-tab-item" key="overview-tab">Overview</v-tab>
        <v-tab class="description-tab-item" key="review-tab">Customer Reviews</v-tab>
        <v-tab class="description-tab-item" key="specification-tab">Specifications</v-tab>
      </v-tabs>

      <v-tabs-items v-model="tab">
        <v-tab-item key="overview-tab">
          <div v-if="description">
            <div v-html="description" class="p-5">
            </div>
          </div>
          <div v-else>
            <p class="p-5">No overview available</p>
          </div>
        </v-tab-item>
        <v-tab-item key="review-tab">
          <div>
            <p class="p-5">No review available</p>
          </div>
        </v-tab-item>
        <v-tab-item key="specification-tab">
          <div>
            <p class="p-5">No Specification available</p>
          </div>
        </v-tab-item>
      </v-tabs-items>
  </div>
</template>

<script>
export default {
  name: "ProductDescription",
  props: ['description'],
  data(){
    return{
      overview: null,
      reviews: null,
      specification: null,
      tab: null,
    }
  }
}
</script>

<style scoped>
.description-tab-item{
  font-size: 15px;
  text-transform: uppercase;
}
</style>