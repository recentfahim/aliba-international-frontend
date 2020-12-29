<template lang="html">
    <section>
        <aside>
            <div class="may-like">
                <div class="may-like-title">
                    Recommended For You
                </div>
                <div class="simple-card-container" style="width: 135px;">
                    <div class="img-container" style="width: 135px; height: 135px;">
                        <a href="#">
                        <img class="simple-card-img" src="//ae01.alicdn.com/kf/Hec8c60c99fc74489997965ef2ff34626u.jpg_220x220q90.jpg" alt="product-image">
                        </a>
                    </div>
                    <div class="simple-card-price">BDT 749.48
                    </div>
                </div>
    
                <div class="simple-card-container" style="width: 135px;">
                    <div class="img-container" style="width: 135px; height: 135px;">
                        <a href="#">
                        <img class="simple-card-img" src="https://ae01.alicdn.com/kf/H5734e9a657e24a02bbe7cf123f93e541u.jpg_220x220q90.jpg" alt="product-image">
                        </a>
                    </div>
                    <div class="simple-card-price">BDT 1,007.21

                    </div>
                </div>    
                
                <div class="simple-card-container" style="width: 135px;">
                    <div class="img-container" style="width: 135px; height: 135px;">
                        <a href="#">
                        <img class="simple-card-img" src="https://ae01.alicdn.com/kf/H1582d077e3de43c493dccda0110d67d8D.jpg_220x220q90.jpg" alt="product-image">
                        </a>
                    </div>
                    <div class="simple-card-price">BDT 754.50
                    </div>   
                </div>               
            </div>
         </aside>

         <aside>
             <div class="product-fix-sns">
                <div class="product-fix-wrap">
                    <div style="visibility: visible;">
                        <div class="sns-shares">
                            <span>
                                 <a href="https://www.facebook.com/sharer/sharer.php?spm=a2g0o.detail.share.1.62e76a26Ov2ZPE&amp;u=https%3A%2F%2Fwww.aliexpress.com%2Fitem%2F4000036855312.html%3Fchannel%3Dfacebook">
                                 </a>
                            </span>
                            <span>
                                 <a href="https://www.facebook.com/sharer/sharer.php?spm=a2g0o.detail.share.1.62e76a26Ov2ZPE&amp;u=https%3A%2F%2Fwww.aliexpress.com%2Fitem%2F4000036855312.html%3Fchannel%3Dfacebook">
                                 </a>
                            </span>
                            <span>
                                 <a href="https://www.facebook.com/sharer/sharer.php?spm=a2g0o.detail.share.1.62e76a26Ov2ZPE&amp;u=https%3A%2F%2Fwww.aliexpress.com%2Fitem%2F4000036855312.html%3Fchannel%3Dfacebook">
                                 </a>
                            </span>
                            <span>
                                 <a href="https://www.facebook.com/sharer/sharer.php?spm=a2g0o.detail.share.1.62e76a26Ov2ZPE&amp;u=https%3A%2F%2Fwww.aliexpress.com%2Fitem%2F4000036855312.html%3Fchannel%3Dfacebook">
                                 </a>
                            </span>
                        </div> 
                        
                    </div>
                </div>
            </div>               
        </aside>
    </section>
</template>

<script>
import { mapState } from 'vuex';
import { getColletionBySlug } from '~/utilities/product-helper';
import ProductDefault from '~/components/elements/product/ProductDefault';

export default {
    name: 'ProductWidgets',
    components: { ProductDefault },
};
</script>

<style lang="scss" scoped>

.may-like {
    -ms-flex-preferred-size: 135px;
    flex-basis: 135px;
    -ms-flex-negative: 0;
    flex-shrink: 0;
    margin-left: 32px;
    text-align: center;
}

.may-like .may-like-title {
    line-height: 15px;
    font-size: 14px;
    color: #999;
    margin-bottom: 7px;
    padding-right: 118px;
    /* display: block; */
}
.simple-card-container {
    text-align: center;
    position: relative;
    width: 134px;
    margin-bottom: 10px;
}
.simple-card-container .img-container {
    position: relative;
    border: 1px solid #f2f2f2;
    overflow: hidden;
    border-radius: 4px;
    width: 135px;
    height: 135px;
}
a:visited {
    color: #fff;
}
a {
    text-decoration: none;
}
.simple-card-container .simple-card-img {
    max-width: 100%;
    position: relative;
    max-height: 100%;
    top: 50%;
    left: 38%;
    transform: translate(-50%, -50%);
    /* display: inline-grid; */
        // padding-right: 15px;
}
img {
    vertical-align: middle;
}

.simple-card-price{
  margin-top: 5px;
  font-size: 12px;
  font-weight: 600;
}

</style>
