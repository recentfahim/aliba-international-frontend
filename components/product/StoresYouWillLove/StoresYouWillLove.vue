<template>
  <v-row class="store">
    <div>
      <div class="loved stores">
        <div class="title-container">
          <div class="title-info">
            <div class="loved-stores-icon">
              <i class="far fa-heart-circle"></i>
            </div>
            <span>Stores You'll Love</span>
          </div>
          <!-- <featured-brands-item></featured-brands-item> -->
        </div>
        <v-row class="ml-0 mr-0 pb-2">

          <v-col md="6">
            <v-row class="product-container">
              <v-col md="8" class="pl-0">
                <l-item-1></l-item-1>
              </v-col>
              <v-col md="4" class="pr-0">
                <v-row>
                  <v-col md="12" class="pr-0-1">
                    <l-item-1></l-item-1>
                  </v-col>
                  <v-col md="12">
                    <l-item-1></l-item-1>
                  </v-col>
                </v-row>
              </v-col>

              <div class="shop-info">
                <div>
                  <img class="store-image"
                       src="http://ae01.alicdn.com/kf/H7bade7b45ecf40e2912da2ab8ab512d2Q.jpg_200x200.jpg_.webp">
                </div>
                <div class="shop-name">
                  <div class="store-info">Focallure Official Store</div>
                  <div class="store-tag">
                    <span>Sexy</span>
                  </div>
                </div>
              </div>
            </v-row>

          </v-col>
          <v-col md="6">
            <v-row class="product-container">
              <v-col md="8" class="pl-0">
                <l-item-1></l-item-1>
              </v-col>
              <v-col md="4" class="pr-0">
                <v-row>
                  <v-col md="12" class="pr-0-1">
                    <l-item-1></l-item-1>
                  </v-col>
                  <v-col md="12">
                    <l-item-1></l-item-1>
                  </v-col>
                </v-row>
              </v-col>

              <div class="shop-info">
                <div>
                  <img class="store-image"
                       src="http://ae01.alicdn.com/kf/H7bade7b45ecf40e2912da2ab8ab512d2Q.jpg_200x200.jpg_.webp">
                </div>
                <div class="shop-name">
                  <div class="store-info">Focallure Official Store</div>
                  <div class="store-tag">
                    <span>Sexy</span>
                  </div>
                </div>
              </div>
            </v-row>

          </v-col>
        </v-row>
      </div>
    </div>
  </v-row>

</template>


<script>
import LItem1 from './L-Item1.vue';

export default {
  name: 'StoresYouWillLove',
  components: {
    LItem1

  }

};

</script>

<style scoped>
.title-container {
  padding: 8px 3px 5px;
  overflow: hidden;
}
.loved-stores-icon {
  height: 30px;
  width: 30px;
  border-radius: 50%;
  background-color: #FFFF00;
  color: #ffffff;
  margin-left: 8px;
  font-size: 20px;
  padding: 0px 28px 0px 0px;
  margin: 10px 0 0 10px;
}

.loved-stores-icon i {
  padding: 5px 0 0 5px;

}

.h3 {

  margin: 6px 0 0px 11px;
  font-size: 18px;

}

.pl-0 {
  height: fit-content;
}

.pr-0-1 {
  margin: 0 0 3px 0;
  /* height: 8em; */
}

.store-image {
  margin: 8px 0 0 0;
  height: 35px;
}

.title-info {
  display: flex;
}

.title-info span {
  font-size: 17px;
  font-weight: bold;
  line-height: 45px;
  margin-left: 10px;
}

.store {
  background-color: #ffffff;
  border-radius: 10px;
  margin-left: 0px;
}

.store-image {
  margin-left: 9px;
}

.store-info {
  font-size: 14px;
  font-weight: bold;
  display: flex;
}

.store-tag {
  background: rgb(255, 239, 229);
  width: 60px;
  text-align: center;
  border-radius: 20px;
}

.product-container {
  margin: 0px;
  background-color: whitesmoke;
  border-radius: 5px;
  padding-bottom: 10px;
}

.shop-name {
  margin-left: 10px;
}

.shop-info {
  display: flex;
}
</style>