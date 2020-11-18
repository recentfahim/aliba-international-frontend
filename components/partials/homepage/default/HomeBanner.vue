<template lang="html">
    <div class="ps-home-banner ps-home-banner--1">
        <div class="ps-container">
            <div class="ps-section__right pl-5">
                <nuxt-link to="/shop" class="ps-collection" v-for="category in categories" :key="category.ID">
                    <div>
                        {{ category.Name }}
                    </div>
                </nuxt-link>
            </div>
            <div class="ps-section__left ml-4">
                <div class="ps-carousel" v-swiper:mySwiper="swiperOption">
                    <div class="swiper-wrapper">
                        <div class="swiper-slide">
                            <div
                                class="ps-banner"
                                :style="{
                                    backgroundImage: `url(/img/slider/home-1/slide-1.jpg)`
                                }"
                            ></div>
                        </div>
                        <div class="swiper-slide">
                            <div
                                class="ps-banner"
                                :style="{
                                    backgroundImage: `url(/img/slider/home-1/slide-2.jpg)`
                                }"
                            ></div>
                        </div>
                        <div class="swiper-slide">
                            <div
                                class="ps-banner"
                                :style="{
                                    backgroundImage: `url(/img/slider/home-1/slide-3.jpg)`
                                }"
                            ></div>
                        </div>
                    </div>
                    <!--Carousel controls-->
                    <div class="swiper-nav">
                        <span class="swiper-arrow swiper-prev"
                            ><i class="icon-chevron-left"></i
                        ></span>
                        <div class="swiper-arrow swiper-next">
                            <i class="icon-chevron-right"></i>
                        </div>
                    </div>
                    <div
                        class="swiper-pagination swiper-pagination-bullets"
                    ></div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'HomeBanner',
    data() {
        return {
            swiperOption: {
                loop: true,
                slidesPerView: 1,
                spaceBetween: 1,
                navigation: {
                    nextEl: '.swiper-next',
                    prevEl: '.swiper-prev'
                }
            },
            categories: []
        };
    },
    mounted(){
        axios.get(`http://localhost:8000/api/v1/category/`).then((response) => {
            this.categories = response.data.data
        })
    }

};
</script>

<style lang="scss" scoped>
.ps-section__left{
    max-height: 425px;
}
</style>
