<template>
    <div>
        <v-row>
            <v-col md="3">
                <Category></Category>
            </v-col>
            <v-col md="6">
                <HomeSlider></HomeSlider>
            </v-col>
            <v-col md="3">
                <SignInSignUp></SignInSignUp>
            </v-col>
        </v-row>
    </div>

</template>

<script>
import HomeSlider from '~/components/home/HomeSlider';
import SignInSignUp from '~/components/home/SignInSignUp';
import Category from '~/components/home/Category';

export default {
    name: "CatSliderSign",
    components: {
        HomeSlider,
        SignInSignUp,
        Category
    }
}
</script>

<style scoped>
</style>