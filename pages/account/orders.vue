<template lang="html">
    <section class="ps-page--my-account">
        <orders />
    </section>
</template>

<script>
import Orders from '~/components/partials/account/Orders';
import HeaderMobile from '~/components/shared/mobile/HeaderMobile';

export default {
    transition: 'zoom',
    middleware: 'authentication',
    components: {
        HeaderMobile,
        Orders,
    },
    data: () => {
        return {
            breadCrumb: [
                {
                    text: 'Home',
                    url: '/'
                },
                {
                    text: 'Invoices'
                }
            ]
        };
    }
};
</script>

<style lang="scss" scoped></style>
