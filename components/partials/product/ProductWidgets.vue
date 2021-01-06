<template lang="html">
    <section>
        <aside>
            <div class="may-like">
                <div class="may-like-title">
                    Recommended For You
                </div>
                <div class="recommended_item_container" v-for="(item, index) in recommended_item" :key="index">
                  <nuxt-link :to="`product/${item.id}`">
                    <div class="recommended_item">
                        <img class="recommended_item_image" :src="item.image" alt="product-image">
                    </div>
                    <div class="recommended_item_price">
                      BDT {{ item.price }}
                    </div>
                  </nuxt-link>
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
    props: ['recommended_item'],
    components: { ProductDefault },
};
</script>

<style lang="scss" scoped>
.recommended_item_container{
  width: 150px;
}
.recommended_item{
  margin-top: 10px;
  padding: 5px;
  border: 1px solid #f2f2f2;
}
.recommended_item_price{
  font-family: OpenSans, Open Sans, Arial, Helvetica, sans-serif, SimSun;
  margin-top: 5px;
  font-size: 12px;
  font-weight: 600;
}

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
