<template lang="html">
    <!-- <v-row class="container"> -->
        <client-only>
            <div class="ps-product__thumbnail " data-vertical="true">
                <figure>
                    <div class="ps-wrapper">
                        <!-- Gallery-->
                        <div class="ps-product__gallery">
                            <div
                                class=" ps-carousel inside swiper"
                                v-swiper:swiperGallery="swiperOptionTop"
                                ref="mySwiper"
                            >
                                <div class="swiper-wrapper">
                                    <div
                                        class="swiper-slide"
                                        v-for="image in product.Pictures"
                                    >
                                        <img :src="image.Url" />
                                    </div>
                                </div>
                                <div class="swiper-nav">
                                    <span class="swiper-arrow swiper-prev">
                                        <i class="icon-chevron-left"></i>
                                    </span>
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
                </figure>
                <!-- Variants -->
                <div class="ps-product__variants">
                    <div
                        class="ps-carousel swiper"
                        v-swiper:swiperVariants="swiperOptionThumbs"
                    >
                        <div class="swiper-wrapper">
                            <div
                                v-for="(image, index) in product.Pictures"
                                :class="
                                    `swiper-slide ${
                                        activeSlide === index ? 'active' : ''
                                    } `
                                "
                                @click="handleClickSlide(index)"
                            >
                                <img :src="image.Url" />
                            </div>
                        </div>
                    </div>
                </div>
            </div>       
        </client-only>
    <!-- </v-row>     -->
</template>

<script>
import { mapState } from 'vuex';
import { baseUrl } from '~/repositories/Repository';

export default {
    name: 'ThumbnailDefault',
    props: ['product'],
    data() {
        return {
            swiperOptionTop: {
                loop: false,
                slidesPerView: 1,
                navigation: {
                    nextEl: '.swiper-next',
                    prevEl: '.swiper-prev'
                }
            },
            swiperOptionThumbs: {
                direction: 'vertical',
                loop: false,
                spaceBetween: 10,
                slidesPerView: 3,
                centeredSlides: false,
                slideToClickedSlide: false
            },
            activeSlide: 0
        };
    },
    methods: {
        handleClickSlide(index) {
            this.activeSlide = index;
            this.swiperVariants.activeIndex = index;
            this.swiperGallery.slideTo(index, 500, false);
        }
    }
};
</script>

<style lang="scss" scoped>

// secpart

.widget-detail-booth-image .util-clearfix {
    zoom: 1;
}

.unite .widget-detail-booth-image .inav .first {
    margin-left: 0;
}
.widget-detail-booth-image .inav .active {
    width: 48px;
    height: 48px;
    border: 2px solid #fe9b0a;
}
.widget-detail-booth-image .inav .active .thumb {
    border: none;
    width: 100%;
    height: 100%;
}
.iwrap a, .widget-detail-booth-image .thumb a {
    display: table-cell;
    text-align: center;
    vertical-align: middle;
}
.widget-detail-booth-image .active .thumb a img {
    max-width: 48px;
    max-height: 48px;
}
.widget-detail-booth-image .inav .active .arrow {
    display: inline-block;
    width: 0;
    height: 0;
    line-height: 0;
    vertical-align: middle;
    border: 5px dashed transparent;
    border-bottom: 5px solid #fe9b0a;
    position: absolute;
    top: -11px;
    left: 20px;
}
.unite .widget-detail-booth-image .inav .first {
    margin-left: 0;
}
.widget-detail-booth-image .util-clearfix:after {
    visibility: hidden;
    display: block;
    height: 0;
    font-size: 0;
    content: " ";
    clear: both;
}
.widget-detail-booth-image .util-clearfix {
    zoom: 1;
}

// subimage

.ps-product--detail .ps-product__thumbnail .ps-product__variants {
    max-width: 70px;
    flex-basis: 100%;
    padding-right: 10px;
}

.ps-product--detail .ps-product__variants .swiper {
    max-height: inherit;
    position: relative;
}
.swiper-container-vertical > .swiper-wrapper {
    -webkit-box-orient: horizontal;
    -webkit-box-direction: normal;
    -webkit-flex-direction: column;
    -ms-flex-direction: column;
    flex-direction: column;
}

element.style {
    transform: translate3d(0px, 0px, 0px);
}
.ps-product--detail .ps-product__variants .swiper-slide {
    cursor: pointer;
    height: auto !important;
    padding-right: 1px;
}
.ps-product--detail .ps-product__variants .swiper-slide img {
    width: 100%;
    opacity: 0.5;
    transition: all 0.4s ease;
    border: 1px solid #d9d9d9;
}
.swiper-container .swiper-notification {
    position: absolute;
    left: 0;
    top: 0;
    pointer-events: none;
    opacity: 0;
    z-index: -1000;
}


</style>