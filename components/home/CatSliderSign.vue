<template>
    <div>
        <v-row>
            <v-col md="3">
                asdasdasd
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

export default {
    name: "CatSliderSign",
    components: {
        HomeSlider,
        SignInSignUp
    }
}
</script>

<style scoped>
</style>