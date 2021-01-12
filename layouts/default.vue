<template lang="html">
    <client-only>
        <v-app>
            <v-main>
                <header-default />
                <header-mobile />
                <nuxt></nuxt>
                <notify />
              <footer-fullwidth />
                <navigation-list />
                <mobile-drawer />
            </v-main>
        </v-app>
    </client-only>
</template>

<script>
import Notify from '~/components/elements/commons/notify';
import NavigationList from '~/components/shared/mobile/NavigationList';
import MobileDrawer from '~/components/shared/mobile/MobileDrawer';
import HeaderDefault from '~/components/shared/headers/HeaderDefault';
import HeaderMobile from '~/components/shared/mobile/HeaderMobile';
import Newsletters from '~/components/partials/commons/Newsletters';
import FooterDefault from '~/components/shared/footers/FooterDefault';
import FooterFullwidth from '~/components/shared/footers/FooterFullwidth';

export default {
    components: { FooterDefault, Newsletters, HeaderMobile, HeaderDefault, MobileDrawer, NavigationList, Notify, FooterFullwidth }
};
</script>

<style lang="scss" scoped></style>
