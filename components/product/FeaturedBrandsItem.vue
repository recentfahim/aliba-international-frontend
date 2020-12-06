<template>
    <div class="product-grid">
        <div >
            <img class="product-image" src="http://ae01.alicdn.com/kf/H0a10dd69f044476fb343c11c72ad9a4a1.png">
            <!--            <img class="product-image" src="https://ae01.alicdn.com/kf/H73f804fdf9d4403182ec701c146d7628R.jpg_200x200.jpg">-->
        </div>
        <div class="product-price">
            Coming soon
        </div>
        <div>
            <span class="countdown"> <i class="far fa-stopwatch"></i></span>
                <span class="float stage">Sale starts in: 2 days </span>
                <!-- <span class="float" data-day="day"> <em data-role="day">2</em> </span>  -->
                <!-- <span class="float day">days</span>  -->
        </div>
    </div>
</template>    

<script>
export default {
name: "FeaturedBrandsItem"
}
</script>

<style scoped>
.product-image{
    border-radius: 9px;
}

</style>