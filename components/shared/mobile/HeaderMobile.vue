<template lang="html">
    <header class="header header--mobile">
        <div class="header__top">
            <div class="header__left">
                <p>Welcome to Aliba International Online Shopping Store !</p>
            </div>
        </div>
        <div class="navigation--mobile">
            <div class="navigation__left">
                <nuxt-link to="/" class="ps-logo">
                    <img src="~/static/img/aliba_logo.jpeg" width="25%" alt="Aliba International" />
                </nuxt-link>
            </div>
            <mobile-header-actions />
        </div>
    </header>
</template>

<script>
import MobileHeaderActions from '~/components/shared/mobile/modules/MobileHeaderActions';
export default {
    name: 'HeaderMobile',
    components: { MobileHeaderActions }
};
</script>

<style lang="scss" scoped></style>
