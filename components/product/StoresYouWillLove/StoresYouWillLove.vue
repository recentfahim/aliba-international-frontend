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
                <v-row class="ml-0 mr-0">
                    
                    <v-col md="6">
                        <v-row>
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
                     <a class="flex" href="https://sale.aliexpress.com/stores_your_love.htm?spm=a2g0o.home.15004.5.387a2145YPl6OR&amp;storeIds=122129648" >
                     <img class="store-image" src="http://ae01.alicdn.com/kf/H7bade7b45ecf40e2912da2ab8ab512d2Q.jpg_200x200.jpg_.webp">
                     <div class="shop-name">
                     <div class="store-info" >Focallure Official Store</div>
                    <span class="store-tag">Sexy</span>
                    </div>
                     </a>
                </div>
                            <!-- <div>
                                <img class="store-image" src="http://ae01.alicdn.com/kf/H7bade7b45ecf40e2912da2ab8ab512d2Q.jpg_200x200.jpg_.webp">
                                <b class="store-info">
                                    Focallure Official Store 
                                </b>    
                                <span class="store-info span">
                                    Sexy
                                </span>
                                
                            </div> -->

                            <!-- <div class="store-info">
                                Focallure Official Store 
                            </div>
                            <div>
                                <span class="float stage">Sexy</span>
                            </div> -->
                        </v-row>
                        <!-- <StoresYouWillLoveItems></StoresYouWillLoveItems> -->
                    </v-col>
                    <v-col md="6">
                        <v-row>
                            <v-col md="8" class="pl-0">
                                <l-item-1></l-item-1>
                            </v-col>
                            <v-col md="4" class="pr-0">
                                <v-row>
                                    <v-col md="12">
                                        <l-item-1></l-item-1>
                                    </v-col>
                                    <v-col md="12">
                                        <l-item-1></l-item-1>
                                    </v-col>
                                </v-row>
                            </v-col>
                        </v-row>
                        <!-- <StoresYouWillLoveItems></StoresYouWillLoveItems> -->
                    </v-col>
                <div class="shop-info">
                     <a class="flex" href="https://sale.aliexpress.com/stores_your_love.htm?spm=a2g0o.home.15004.5.387a2145YPl6OR&amp;storeIds=122129648" >
                     <img class="store-image" src="http://ae01.alicdn.com/kf/H7bade7b45ecf40e2912da2ab8ab512d2Q.jpg_200x200.jpg_.webp">
                     <div class="shop-name">
                     <div class="store-info" >Focallure Official Store</div>
                     <span class="store-tag">Sexy</span>
                    </div>
                     </a>
                </div>
                </v-row>    
            </div>    
        </div>  
    </v-row>
    
</template>


<script>
import LItem1 from './L-Item1.vue'

    export default {
    name: "StoresYouWillLove",
    components: {
        LItem1
        
    }

}
    
</script>

<style scoped>
.loved-stores-icon{
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
.loved-stores-icon i{
    padding: 5px 0 0 5px;

}
.h3{
    
    margin: 6px 0 0px 11px;
    font-size: 18px;

}
.pl-0{
    height: fit-content;
}
.pr-0-1{
margin: 0 0 3px 0;
/* height: 8em; */
}
.store-image{
    margin: 8px 0 0 0;
    height: 35px;     
}
.title-info{
 display: flex;
}
.title-info span{
    font-size: 17px;
    font-weight: bold;
    line-height: 45px;
    margin-left: 10px;
}
.store{
    background-color: #ffffff;
    border-radius: 10px;
    margin-left: 0px;
}
.store-image{
    margin-left: 15px;
}
.store-info{
    font-size: 14px;
    font-weight: bold;
}
.store-tag{
    background: rgb(255, 239, 229);
    margin: 0 0 0 15px;
}
</style>