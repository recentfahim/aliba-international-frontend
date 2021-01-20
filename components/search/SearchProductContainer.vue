<template>
  <v-row>
    <v-col md="2" v-for="(product, index) in products" :key="index">
      <SearchProduct :product="product"/>
    </v-col>
  </v-row>
</template>

<script>
import SearchProduct from '~/components/search/SearchProduct';
export default {
name: "SearchProductContainer",
  props: ['products'],
  components: { SearchProduct }
}
</script>

<style scoped>

</style>