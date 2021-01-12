<template lang="html">
    <section class="ps-page--my-account">
        <invoice-detail />
    </section>
</template>

<script>
import InvoiceDetail from '~/components/partials/account/InvoiceDetail';

export default {
    transition: 'zoom',
    middleware: 'authentication',
    components: {
        InvoiceDetail,
    },
    data: () => {
        return {
        };
    }
};
</script>

<style lang="scss" scoped></style>
