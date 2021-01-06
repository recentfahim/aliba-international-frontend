<template lang="html">
  <div>
    <v-row>
      <v-col md="2">
        <div class="similar-product-title-container">
          <div class="similar-product-title">
            <div class="similar-product-title-text">
              Similar Product
            </div>
          </div>
        </div>
      </v-col>
      <v-col md="10">
        <SimilarProductContainer :similar_products="similar_products"/>
      </v-col>
    </v-row>
  </div>
<!--  <div class="main">
    <div class="store-info">
      <div class="store-info-top notranslate">
        <div class="shop-name" data-spm="100005" data-spm-max-idx="1">
          <a target="_blank" rel="noopener noreferrer" href="#">
            Beidao Glasses Store
          </a>
        </div>
      </div>
      <div class="store-info-content">
        <div class="top-seller-label">
          <a href="#">
          <svg id="icon-topseller" viewBox="0 0 1024 1024">
            <path d="M341.333333 512v426.666667l170.666667-128 170.666667 128V512z" fill="#E64A33">
            </path>
            <path d="M512 384m-277.333333 0a277.333333 277.333333 0 1 0 554.666666 0 277.333333 277.333333 0 1 0-554.666666 0Z" fill="#FAED29">
            </path>
            <path d="M512 469.333333l-100.309333 52.736 19.157333-111.701333-81.152-79.104 112.128-16.298667L512 213.333333l50.176 101.632 112.128 16.298667-81.152 79.104 19.2 111.701333z" fill="#BB8C2C">
            </path>
          </svg>
          <span class="top-seller-text">Top Brands
          </span>
          </a>
        </div>
        <div class="store-info-data">
            <div class="positive-fdbk">98.5%&nbsp;
              <span class="store-info-text">Positive Feedback
              </span>
            </div>
            <div class="follower-num">469.2K&nbsp;
              <span class="store-info-text">Followers
              </span>
            </div>
        </div>
        <div class="store-info-contact">
          <div class="contact-block">
            <a rel="nofollow noopener noreferrer">
            <svg class="icon-svg img-contact" style="font-size: 16px;">
              <use xlink:href="#icon-contact">
              </use>
            </svg>
            <span class="contact-text">Contact
            </span>
            </a>
          </div>
        </div>
      </div>

      <div class="instore-info-rcmds">

        <div class="simple-card-container" style="width: 108px;">
          <div class="img-container" style="width: 108px; height: 108px;">
            <a href="http://localhost:4000/product/abb-521691559512">
              <img class="simple-card-img" src="https://ae01.alicdn.com/kf/Hec8c60c99fc74489997965ef2ff34626u.jpg_220x220q90.jpg" alt="product-image">
            </a>
          </div>
          <div class="simple-card-price">BDT 966.98
          </div>
        </div>
        <div class="simple-card-container" style="width: 108px;">
          <div class="img-container" style="width: 108px; height: 108px;">
            <a href="//www.aliexpress.com/item/4000670522499.html?gps-id=pcDetailBottomMoreThisSeller&amp;scm=1007.13339.169870.0&amp;scm_id=1007.13339.169870.0&amp;scm-url=1007.13339.169870.0&amp;pvid=6aaa400b-a38f-4b4d-bb47-1d9364e4c3a2&amp;_t=gps-id:pcDetailBottomMoreThisSeller,scm-url:1007.13339.169870.0,pvid:6aaa400b-a38f-4b4d-bb47-1d9364e4c3a2,tpp_buckets:668%230%23131923%2337_668%23888%233325%2317_668%232846%238112%231997_668%232717%237564%23680_668%231000022185%231000066058%230_668%233468%2315607%2394">
            <img class="simple-card-img" src="//ae01.alicdn.com/kf/Hb9de600a67b64a13bc3495a49fb03c3dM.jpg_480x480q90.jpg_.webp" alt="product-image">
            </a>
          </div>
          <div class="simple-card-price">BDT 1,005.15
          </div>
        </div>
        <div class="simple-card-container" style="width: 108px;">
          <div class="img-container" style="width: 108px; height: 108px;">
            <a href="//www.aliexpress.com/item/4000670522499.html?gps-id=pcDetailBottomMoreThisSeller&amp;scm=1007.13339.169870.0&amp;scm_id=1007.13339.169870.0&amp;scm-url=1007.13339.169870.0&amp;pvid=6aaa400b-a38f-4b4d-bb47-1d9364e4c3a2&amp;_t=gps-id:pcDetailBottomMoreThisSeller,scm-url:1007.13339.169870.0,pvid:6aaa400b-a38f-4b4d-bb47-1d9364e4c3a2,tpp_buckets:668%230%23131923%2337_668%23888%233325%2317_668%232846%238112%231997_668%232717%237564%23680_668%231000022185%231000066058%230_668%233468%2315607%2394">
            <img class="simple-card-img" src="//ae01.alicdn.com/kf/Hb9de600a67b64a13bc3495a49fb03c3dM.jpg_480x480q90.jpg_.webp" alt="product-image">
            </a>
          </div>
          <div class="simple-card-price">BDT 1,034.84
          </div>
        </div>
        <div class="simple-card-container" style="width: 108px;">
          <div class="img-container" style="width: 108px; height: 108px;">
            <a href="//www.aliexpress.com/item/4000670522499.html?gps-id=pcDetailBottomMoreThisSeller&amp;scm=1007.13339.169870.0&amp;scm_id=1007.13339.169870.0&amp;scm-url=1007.13339.169870.0&amp;pvid=6aaa400b-a38f-4b4d-bb47-1d9364e4c3a2&amp;_t=gps-id:pcDetailBottomMoreThisSeller,scm-url:1007.13339.169870.0,pvid:6aaa400b-a38f-4b4d-bb47-1d9364e4c3a2,tpp_buckets:668%230%23131923%2337_668%23888%233325%2317_668%232846%238112%231997_668%232717%237564%23680_668%231000022185%231000066058%230_668%233468%2315607%2394">
            <img class="simple-card-img" src="//ae01.alicdn.com/kf/Hd4907de1c7b34a5ba9a4beece3286735K.jpg_480x480q90.jpg_.webp" alt="product-image">
            </a>
          </div>
          <div class="simple-card-price">BDT 810.91
          </div>
        </div>
        <div class="simple-card-container" style="width: 108px;">
          <div class="img-container" style="width: 108px; height: 108px;">
            <a href="//www.aliexpress.com/item/4000670522499.html?gps-id=pcDetailBottomMoreThisSeller&amp;scm=1007.13339.169870.0&amp;scm_id=1007.13339.169870.0&amp;scm-url=1007.13339.169870.0&amp;pvid=6aaa400b-a38f-4b4d-bb47-1d9364e4c3a2&amp;_t=gps-id:pcDetailBottomMoreThisSeller,scm-url:1007.13339.169870.0,pvid:6aaa400b-a38f-4b4d-bb47-1d9364e4c3a2,tpp_buckets:668%230%23131923%2337_668%23888%233325%2317_668%232846%238112%231997_668%232717%237564%23680_668%231000022185%231000066058%230_668%233468%2315607%2394">
            <img class="simple-card-img" src="//ae01.alicdn.com/kf/HTB1gfbFPpXXXXc1XVXXq6xXFXXXz.jpg_480x480q90.jpg_.webp" alt="product-image">
            </a>
          </div>
          <div class="simple-card-price">BDT 296.88
          </div>
        </div>
        <div class="simple-card-container" style="width: 108px;">
          <div class="img-container" style="width: 108px; height: 108px;">
            <a href="//www.aliexpress.com/item/4000670522499.html?gps-id=pcDetailBottomMoreThisSeller&amp;scm=1007.13339.169870.0&amp;scm_id=1007.13339.169870.0&amp;scm-url=1007.13339.169870.0&amp;pvid=6aaa400b-a38f-4b4d-bb47-1d9364e4c3a2&amp;_t=gps-id:pcDetailBottomMoreThisSeller,scm-url:1007.13339.169870.0,pvid:6aaa400b-a38f-4b4d-bb47-1d9364e4c3a2,tpp_buckets:668%230%23131923%2337_668%23888%233325%2317_668%232846%238112%231997_668%232717%237564%23680_668%231000022185%231000066058%230_668%233468%2315607%2394">
            <img class="simple-card-img" src="//ae01.alicdn.com/kf/H1b645e59225946b79f7eeefcc466fbd7u.jpg_480x480q90.jpg_.webp" alt="product-image">
            </a>
          </div>
          <div class="simple-card-price">BDT 770.20
          </div>
        </div>
      </div>
    </div>
  </div>        -->
</template>

<script>
import SimilarProductContainer from '~/components/product/SimilarProductContainer';
export default {
  name: 'SecondaryPart',
  components: { SimilarProductContainer },
  props: ['similar_products'],
//   components: { Rating },

}
</script>s

<style  lang="scss" scoped>
.similar-product-title-container{
  display: table;
  height: 250px;
  overflow: hidden;
}
.similar-product-title{
  display: table-cell;
  vertical-align: middle;
}
.similar-product-title-text{
  font-family: OpenSans, Open Sans, Arial, Helvetica, sans-serif, SimSun;
  font-size: 18px;
  font-weight: bold;
  margin-left: 20px;
}
</style>