<template lang="html">
    <div>
        <h1>{{ product.Title }}</h1>
        <div class="ps-product__meta">
            <p>
                Brand:
                <nuxt-link to="/shop">
                    <a class="ml-2 text-capitalize">
                        {{ product.ProviderType }}
                    </a>
                </nuxt-link>
            </p>
            <div class="ps-product__rating">
                <rating />
                <span>(1 review)</span>
            </div>
        </div>
        <h4 v-if="product.is_sale === true" class="ps-product__price sale">
            <del class="mr-2"> $ {{ product.Price.ConvertedPriceWithoutSign }}</del>
            ${{ product.Price.ConvertedPriceWithoutSign }}
        </h4>
        <h4 v-else class="ps-product__price">
            ${{ product.Price.ConvertedPriceWithoutSign }}
        </h4>
    </div>
</template>

<script>
import Rating from '~/components/elements/Rating';
export default {
    name: 'ModuleProductInfo',
    components: { Rating },
    props: ['product']
};
</script>

<style lang="scss" scoped></style>
