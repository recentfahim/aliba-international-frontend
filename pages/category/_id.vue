<template>
    <div class="martfury mt-5 mb-5" v-if="pageLoading">
        <div class="d-flex justify-content-center text-success">
        <div class="spinner-border" role="status">
            <span class="sr-only">Loading...</span>
        </div>
        </div>
    </div>

    <div class="martfury" v-else>
        <div class="ps-page--product pb-lg-5">
            <div class="ps-container">
                <div class="ps-page__container">
                    <Categoryproducts/>
                </div>
            </div>
        </div>
    </div>


</template>

<script>
import Categoryproducts from '~/components/product/Categoryproducts.vue'
export default {
  components: { Categoryproducts },

}
</script>

<style>

</style>