<template lang="html">
    <div class="ps-product--detail ps-product--fullwidth">
        <div class="ps-product__header">
            <thumbnail-default :product="product" />

            <information-default :product="product" />
        </div>
            <!-- <default-description />-->
            
            <!-- <v-row >      -->
            <!-- <v-col class="col-md-4">   -->
                <div class="images-view-wrap">
                    <ul class="images-view-list">
                        <li class="active">
                            <div class="images-view-item">
                                <img src="https://ae01.alicdn.com/kf/H858d4c1fd2694c658274f932b19fa4e2Q/KINGSEVEN-Aluminum-Men-s-Sunglasses-Polarized-Lens-Brand-Design-Temples-Sun-glasses-Coating-Mirror-Glasses-Oculos.jpg_50x50.jpg_.webp" data-spm-anchor-id="a2g0o.detail.1000017.i0.62e76a26ItUPoN">
                                    </span>
                            </div>
                        </li>
                        <li>
                        <div class="col-md-2">    
                            <div  class="images-view-item">
                                <img src="https://ae01.alicdn.com/kf/H75e73bcaa60145ce84b0baade309336au/KINGSEVEN-Aluminum-Men-s-Sunglasses-Polarized-Lens-Brand-Design-Temples-Sun-glasses-Coating-Mirror-Glasses-Oculos.jpg_50x50.jpg_.webp">
                            </div>
                        </div>    
                        </li>
                        <li>
                         <div class="col-md-2">    
                            <div class="images-view-item">
                                <img src="https://ae01.alicdn.com/kf/H8cdd5841b36c47f0969d2e4c678a26411/KINGSEVEN-Aluminum-Men-s-Sunglasses-Polarized-Lens-Brand-Design-Temples-Sun-glasses-Coating-Mirror-Glasses-Oculos.jpg_50x50.jpg_.webp">
                            </div>
                        </div>    
                        </li>
                        <li>
                        <div class="col-md-2">     
                            <div class="images-view-item">
                                <img src="https://ae01.alicdn.com/kf/H75e73bcaa60145ce84b0baade309336au/KINGSEVEN-Aluminum-Men-s-Sunglasses-Polarized-Lens-Brand-Design-Temples-Sun-glasses-Coating-Mirror-Glasses-Oculos.jpg_50x50.jpg_.webp">
                            </div>
                        </div>    
                        </li>
                        <li>
                        <div class="col-md-2">     
                            <div  class="images-view-item">
                                <img src="https://ae01.alicdn.com/kf/H75e73bcaa60145ce84b0baade309336au/KINGSEVEN-Aluminum-Men-s-Sunglasses-Polarized-Lens-Brand-Design-Temples-Sun-glasses-Coating-Mirror-Glasses-Oculos.jpg_50x50.jpg_.webp">
                            </div>
                        </div>    
                        </li>
                    </ul>
                </div> 
            <!-- </v-col> -->
            <!-- </v-row>    -->

                
    </div>

</template>

<script>
import DefaultDescription from '~/components/elements/detail/modules/DefaultDescription';
import InformationDefault from '~/components/elements/detail/information/InformationDefault';
import ThumbnailDefault from '~/components/elements/detail/thumbnail/ThumbnailDefault';
export default {
    name: 'ProductDetailFullwidth',
    props: ['product'],
    components: { ThumbnailDefault, InformationDefault, DefaultDescription }
};
</script>

<style lang="scss" scoped>
.images-view-wrap {
    // width: 100%;
    overflow-x: auto;
}
.images-view-wrap .images-view-list {
    background-color: #fff;
    padding: 0;
    margin: 15px 200px 20px -380px;
    list-style-type: none;
    text-align: center;
}
.images-view-wrap .images-view-list li {
    display: inline-block;
    vertical-align: middle;
    box-shadow: inset 0 0 0 1px #ccc;
    border-radius: 3px;
    cursor: pointer;
    margin-right: 11px;
}
.images-view-wrap .images-view-list li .images-view-item {
    width: 54px;
    height: 54px;
    display: -ms-flexbox;
    display: flex;
    -ms-flex-pack: center;
    justify-content: center;
    -ms-flex-align: center;
    align-items: center;
    position: relative;
}
.images-view-wrap .images-view-list li .images-view-item img {
    max-width: 50px;
    max-height: 50px;
}
.images-view-wrap .images-view-list li .images-view-item .play-icon {
    position: absolute;
    top: 50%;
    left: 50%;
    margin: -8px 0 0 -8px;
    display: inline-block;
    width: 16px;
    height: 16px;
    background: url(data:image/png;base64,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);
    background-repeat: no-repeat;
    background-size: contain;
}

product-store-banner {
    overflow: hidden;
    max-width: 1200px;
    width: 100%;
    margin: 20px auto;
    border-radius: 16px;
    height: 56px;
}

// extra hidden styles
.ps-product--detail {
    margin-bottom: 0px;
}
.product-store-banner {
    overflow: hidden;
    max-width: 1200px;
    width: 100%;
    margin: 20px auto;
    border-radius: 16px;
    height: 56px;
}

</style>
