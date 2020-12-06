<template>
    <Hooper>
        <Slide class="slide">
            <img src="https://ae01.alicdn.com/kf/Hcd6a6e1e18d64382a779f10d6aa1dd2br.png" class="slider-image">
        </Slide>
        <Slide class="slide">
            <img src="https://ae01.alicdn.com/kf/Hbbd5fb65fd1449dd8f81a576a65fdadbi.png" class="slider-image">
        </Slide>
        <Slide class="slide">
            <img src="https://ae01.alicdn.com/kf/H2e6bc5693ed94fefac610a8569b42a255.png" class="slider-image">
        </Slide>
        <Slide class="slide">
            <img src="https://ae01.alicdn.com/kf/H3ec0206b843a4150ab3d7eb4c87bc5aea.png" class="slider-image">
        </Slide>
        <Slide class="slide">
            <img src="https://ae01.alicdn.com/kf/Hcd6a6e1e18d64382a779f10d6aa1dd2br.png" class="slider-image">
        </Slide>
        <Slide class="slide">
            <img src="https://ae01.alicdn.com/kf/Hbbd5fb65fd1449dd8f81a576a65fdadbi.png" class="slider-image">
        </Slide>
        <Slide class="slide">
            <img src="https://ae01.alicdn.com/kf/H723e73fda6c14518b369f9817830b9a4E.png" class="slider-image">
        </Slide>
        <Slide class="slide">
            <img src="https://ae01.alicdn.com/kf/H9042e46bfd16459f94367fddefdfdc4cZ.png" class="slider-image">
        </Slide>
        <Slide class="slide">
            <img src="https://ae01.alicdn.com/kf/Ha61225661fcd4364b1eaab9a2fa142e7s.png" class="slider-image">
        </Slide>
        <Slide class="slide">
            <img src="https://ae01.alicdn.com/kf/H0b4e85d24c2c473f810c4577226f72fbs.png" class="slider-image">
        </Slide>
        <hooper-navigation slot="hooper-addons"></hooper-navigation>
        <hooper-pagination slot="hooper-addons"></hooper-pagination>
    </Hooper>
</template>

<script>
import { Slide, Hooper, Navigation as HooperNavigation, Pagination as HooperPagination} from 'hooper'
export default {
    name: "HomeSlider",
    components: {
        Slide,
        Hooper,
        HooperNavigation,
        HooperPagination

    }
}
</script>

<style scoped>
.hooper{
    height: auto;
}
.hooper-slide {
    border-radius: 10px;
}
.slide {
    font-size: 100px;
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
}
.slider-image{
    height: 275px;
    width: 688px;
    border-radius: 10px;
}
</style>