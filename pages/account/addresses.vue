<template lang="html">
    <section class="ps-page--my-account">
        <addresses />
    </section>
</template>

<script>
import Addresses from '~/components/partials/account/Addresses';

export default {
    components: {
        Addresses,
    },
    transition: 'zoom',
    middleware: 'authentication',
    data: () => {
        return {
        };
    }
};
</script>

<style lang="scss" scoped></style>
