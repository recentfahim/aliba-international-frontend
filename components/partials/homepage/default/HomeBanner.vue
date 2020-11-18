<template lang="html">
    <div class="ps-home-banner ps-home-banner--1">
        <div class="ps-container">
            <div class="ps-section__right pl-5">
                <ul role="menu" class="next-menu next-ver home-category">
                    <li role="menuitem" aria-haspopup="true" aria-expanded="false" tabindex="0" class="next-menu-item" v-for="category in categories">
                        <div class="next-menu-item-inner">
                            <span class="next-menu-item-text">
                                <div class="c-menu">
                                    <p>
                                        <a href="/shop" class="f-14 c-name">{{ category.Name }}</a>
                                    </p>
                                </div>
                            </span>
                            <i class="next-icon next-icon-arrow-right next-medium next-menu-icon-arrow"></i>
                        </div>
                    </li>
                </ul>
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
.next-menu, .next-menu *, .next-menu :after, .next-menu :before {
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
}
.next-menu {
    position: relative;
    min-width: 100px;
    margin: 0;
    list-style: none;
    border: 1px solid #dcdee3;
    border-radius: 3px;
    -webkit-box-shadow: none;
    box-shadow: none;
    line-height: 32px;
    font-size: 12px;
    -webkit-animation-duration: .3s;
    animation-duration: .3s;
    -webkit-animation-timing-function: ease;
    animation-timing-function: ease;
}

.home-category {
    width: 300px;
    border: 0!important;
    -webkit-box-shadow: none;
    box-shadow: none;
}

.home-category .next-menu-item, .home-category .next-menu-item-inner {
    height: 51px;
}

.home-category .next-menu-item {
    padding: 0;
}

.next-menu-item {
    position: relative;
    padding: 0 20px;
    -webkit-transition: background .1s linear;
    -o-transition: background .1s linear;
    transition: background .1s linear;
    color: #333;
    cursor: pointer;
}

.next-menu-item:hover{
    a{
        color: red;
    }
}

.home-category .next-menu-item .next-menu-item-inner {
    border-left: 2px solid #fff;
}

.home-category .next-menu-item, .home-category .next-menu-item-inner {
    height: 35px;
}

.next-menu-item-inner {
    height: 32px;
    font-size: 12px;
    overflow: hidden;
    -o-text-overflow: ellipsis;
    text-overflow: ellipsis;
    white-space: nowrap;
    word-wrap: normal;
}

.next-menu-item-text {
    vertical-align: middle;
}

.home-category .c-menu {
    padding: 5px 22px 0;
}

.home-category p {
    margin: 0;
    -o-text-overflow: ellipsis;
    text-overflow: ellipsis;
    overflow: hidden;
}

.home-category .c-name {
    margin-right: 10px;
    font-weight: 700;
}
</style>
