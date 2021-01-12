<template lang="html">
    <section class="ps-page--my-account">
        <user-information />
    </section>
</template>
<script>
import UserInformation from '~/components/partials/account/UserInformation';
import HeaderMobile from '~/components/shared/mobile/HeaderMobile';

export default {
    // middleware: 'authentication',
    transition: 'zoom',
    components: {
        HeaderMobile,
        UserInformation
    },
    data: () => {
        return {
        };
    }
};
</script>

<style lang="scss" scoped></style>
