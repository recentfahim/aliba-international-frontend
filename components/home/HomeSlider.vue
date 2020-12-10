<template>
    <Hooper>
        <Slide class="slide" v-for="(banner, index) in banners" :key="index">
            <img :src="banner.PictureUrl" class="slider-image">
        </Slide>
        <hooper-navigation slot="hooper-addons"></hooper-navigation>
        <hooper-pagination slot="hooper-addons"></hooper-pagination>
    </Hooper>
</template>

<script>
import { Slide, Hooper, Navigation as HooperNavigation, Pagination as HooperPagination} from 'hooper'
import axios from 'axios';
export default {
    name: "HomeSlider",
    components: {
        Slide,
        Hooper,
        HooperNavigation,
        HooperPagination

    },

    data(){
      return{
        banners: null
      }
    },

    created() {
      axios.get(process.env.baseURL + `banners`).then((response) => {
        this.banners = response.data.data
      })
    }
}
</script>

<style scoped>
.hooper{
    height: auto;
}
.hooper-slide {
    border-radius: 10px;
}
.slide {
    font-size: 100px;
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
}
.slider-image{
    height: 275px;
    width: 688px;
    border-radius: 10px;
}
</style>