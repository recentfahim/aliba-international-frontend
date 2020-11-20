<template lang="html">
    <div class="ps-product">
        <div class="ps-product__thumbnail">
            <nuxt-link :to="`/product/${product.Id}`">
                <img
                    :src="product.MainPictureUrl"
                    alt="martfury"
                />
            </nuxt-link>
<!--            <div v-if="product.IsSellAllowed === true" class="ps-product__badge">sale</div>-->
        </div>
        <div class="ps-product__container">
            <nuxt-link to="/shop" class="ps-product__vendor">
                {{ product.ProviderType }}
            </nuxt-link>
            <div class="ps-product__content">
                <nuxt-link
                    :to="`/product/${product.id}`"
                    class="ps-product__title"
                >
                    {{ product.Title }}
                </nuxt-link>
                <div class="ps-product__rating">
<!--                    <rating />-->
<!--                    <span>{{ product.ratingCount }}</span>-->
                </div>
                <p
                    v-if="product.IsSellAllowed === true"
                    class="ps-product__price sale"
                >
                    BDT 500
                    <del class="ml-2">
                        BDT 500
                    </del>
                </p>
                <p v-else class="ps-product__price">
                    BDT 500
                </p>
            </div>
            <div class="ps-product__content hover">
                <nuxt-link :to="`/product/${product.id}`">
                    <a class="ps-product__title">{{ product.Title }}</a>
                </nuxt-link>
                <p
                    v-if="product.IsSellAllowed === true"
                    class="ps-product__price sale"
                >
                    BDT 500
                    <del class="ml-2"> BDT 500</del>
                </p>
                <p v-else class="ps-product__price">BDT 500 }}</p>
            </div>
        </div>
        <v-dialog v-model="quickviewDialog" width="1200">
            <div class="ps-dialog">
                <a
                    class="ps-dialog__close"
                    @click.prevent="quickviewDialog = false"
                >
                    <i class="icon icon-cross"></i>
                </a>
                <product-quickview :product="product" />
            </div>
        </v-dialog>
    </div>
</template>
<script>
import { mapState } from 'vuex';
import { baseUrl } from '~/repositories/Repository';
import Rating from '../Rating';
import ProductQuickview from '~/components/elements/detail/ProductQuickview';

export default {
    components: { ProductQuickview, Rating },
    props: ['product'],

    computed: {
        ...mapState({
            cartItems: state => state.cart.cartItems,
            currency: state => state.app.currency
        }),
        baseUrl() {
            return baseUrl;
        },
        isSale() {
            if (this.product.is_sale) {
                return true;
            }
            return false;
        }
    },

    data: () => ({
        productRating: 5,
        productModal: false,
        productPreload: true,
        isImageLoaded: false,
        quickviewDialog: false
    }),
    methods: {
        handleAddToCart() {
            let item = {
                id: this.product.id,
                quantity: 1,
                price: this.product.price
            };
            this.$store.dispatch('cart/addProductToCart', item);
            this.getCartProduct(this.cartItems);
            this.$notify({
                group: 'addCartSuccess',
                title: 'Success!',
                text: `${this.product.title} has been added to your cart!`
            });
        },

        handleAddItemToWishlist() {
            let item = {
                id: this.product.id
            };

            this.$store.dispatch('wishlist/addItemToWishlist', item);
            this.$notify({
                group: 'addCartSuccess',
                title: 'Add to wishlist!',
                text: `${this.product.title} has been added to your wishlist !`
            });
        },

        handleAddItemToCompare() {
            let item = {
                id: this.product.id
            };
            this.$store.dispatch('compare/addItemToCompare', item);
            this.$notify({
                group: 'addCartSuccess',
                title: 'Add to compare!',
                text: `${this.product.title} has been added to your compare !`
            });
        },

        async getCartProduct(products) {
            let listOfIds = [];
            products.forEach(item => {
                listOfIds.push(item.id);
            });
            const response = await this.$store.dispatch(
                'product/getCartProducts',
                listOfIds
            );
            if (response) {
                this.$store.commit('cart/setLoading', false);
            }
        }
    },
    mounted() {
        console.log(this.product)
    }
};
</script>
