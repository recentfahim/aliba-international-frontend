<template>
    <v-row>
        <v-col md="6" class="pl-0">
            <div class="featured-brands">
                <div class="title-container">
                    <div class="title-info">
                        <div class="featured-brands-icon">
                           <i class="fab fa-creative-commons-share"></i>
                        </div>
                        <h3>Featured Brands</h3>
                    </div>
                    <!-- <featured-brands-item></featured-brands-item> -->
                </div>
                <v-row class="ml-0 mr-0">
                    <v-col md="6">
                        <FeaturedBrandsItem></FeaturedBrandsItem>
                    </v-col>
                    <v-col md="6">
                        <FeaturedBrandsItem></FeaturedBrandsItem>
                    </v-col>
                </v-row>    
            </div>    
        </v-col>
        <v-col md="6" class="pr-0">
            <StoresYouWillLove></StoresYouWillLove>
        </v-col>  
    </v-row>
    
</template>

<script>
import FeaturedBrandsItem from '~/components/product/FeaturedBrandsItem';



    export default {
    name: "FeaturedBrands",
    components: {
        FeaturedBrandsItem
    }

}
</script>

<style scoped>
.top-selection{
    height: 275px;
    background-color: #ffffff;
    border-radius: 10px;
}
.view-more{
    float: right;
    line-height: 24px;
    color: #999;
    font-size: 12px;
    white-space: nowrap;
    position: absolute;
    right: 10px;
}

.title-container {
    padding: 16px 5px 12px;
    overflow: hidden;
}
.top-ranking-icon{
    height: 30px;
    width: 30px;
    border-radius: 50%;
    background-color: #3fa6f5;
    color: #ffffff;
}
.top-ranking-icon i{
    padding: 7px 9px;
    font-size: 15px;
}
.new-arrival-icon{
    height: 30px;
    width: 30px;
    border-radius: 50%;
    background-color: #3fa6f5;
    color: #ffffff;
}
.new-arrival-icon i{
    padding: 7px 7px;
    font-size: 15px;
}
.title-info{
    display: flex;
    position: relative;
}
.title-info h3{
    color: #000;
    margin: 6px 0px 0 10px;
    padding: 0 2px;
    line-height: 20px;
    font-size: 16px;
    font-weight: 900;
    font-family: OpenSans,Open Sans,Arial,Helvetica,sans-serif,SimSun,宋体;
}
.featured-brands{
    background-color: #ffffff;
    border-radius: 10px;
    padding-bottom: 12px;
}
.featured-brands-icon{
    height: 30px;
    width: 30px;
    border-radius: 50%;
    background-color: #bd2e06;
    color: #ffffff;
    margin-left: 8px;
}
.featured-brands-icon i{
    font-size: 18px;
    font-size: 18px;
    padding: 6px 0px 0px 6px;

}
</style>