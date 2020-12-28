<template lang="html">
    <div class="ps-product__shopping d-block mb-0">
      <div>
        <figure>
            <figcaption>Quantity</figcaption>
            <div class="form-group--number">
                <button class="up" @click.prevent="handleIncreaseQuantity">
                    <i class="fa fa-plus"></i>
                </button>
                <button class="down" @click.prevent="handleDescreaseQuantity">
                    <i class="fa fa-minus"></i>
                </button>
                <input
                    v-model="quantity"
                    class="form-control"
                    type="text"
                    disabled
                />
            </div>
        </figure>
      </div>
      <div class="d-flex mt-4">
        <div>
          <a class="btn-buy-now" href="#" @click.prevent="">
            Buy Now
          </a>
        </div>

        <div class="ml-2">
          <a
              class="btn-add-to-cart"
              href="#"
              @click.prevent="handleAddToCart"
          >
              Add to Cart
          </a>
        </div>

        <div class="ps-product__actions ml-2">
            <a href="#">
                <i class="icon-heart"></i>
            </a>
        </div>
      </div>
    </div>
</template>

<script>
import { mapState } from 'vuex';

export default {
    name: 'ModuleProductShopping',
    props: ['product'],
    computed: {
        ...mapState({
            cartItems: state => state.cart.cartItems
        })
    },
    data() {
        return {
            quantity: 1
        };
    },
    methods: {
        handleIncreaseQuantity() {
            this.quantity++;
        },

        handleDescreaseQuantity() {
            if (this.quantity > 1) {
                this.quantity--;
            }
        },

        handleAddToCart(isBuyNow) {
            const cartItemsOnCookie = this.$cookies.get('cart', {
                parseJSON: true
            });
            let existItem;
            if (cartItemsOnCookie) {
                existItem = cartItemsOnCookie.cartItems.find(
                    item => item.id === this.product.id
                );
            }

            let item = {
                id: this.product.id,
                quantity: this.quantity,
                price: this.product.price
            };
            if (existItem !== undefined) {
                if (this.quantity + existItem.quantity > 10) {
                    this.$notify({
                        group: 'addCartSuccess',
                        title: 'Waring!',
                        text: `Can't add more than 10 items`
                    });
                    if (isBuyNow && isBuyNow === true) {
                        setTimeout(
                            function() {
                                this.$router.push('/account/checkout');
                            }.bind(this),
                            500
                        );
                    }
                } else {
                    this.addItemToCart(item);
                }
            } else {
                this.addItemToCart(item);
            }
        },

        addItemToCart(payload) {
            this.$store.dispatch('cart/addProductToCart', payload);
            this.getCartProduct(this.cartItems);
            this.$notify({
                group: 'addCartSuccess',
                title: 'Success!',
                text: `${this.product.title} has been added to your cart!`
            });
        },

        async getCartProduct(products) {
            let listOfIds = [];
            products.forEach(item => {
                listOfIds.push(item.id);
            });
            await this.$store.dispatch('product/getCartProducts', listOfIds);
        },

        async loadCartProducts() {
            const cartItemsOnCookie = this.$cookies.get('cart', {
                parseJSON: true
            });
            let queries = [];
            cartItemsOnCookie.cartItems.forEach(item => {
                queries.push(item.id);
            });
            if (this.cartItems.length > 0) {
                await this.$store.dispatch('product/getCartProducts', queries);
            } else {
                this.$store.commit('product/setCartProducts', null);
            }
        }
    }
};
</script>

<style lang="scss" scoped>
.btn-buy-now{
  border-style: solid;
  background-color: #ff4747;
  border-color: transparent;
  border-radius: 4px;
  padding: 6px 30px;
  color: #fff;
  height: 44px;
  font-size: 20px;
  font-weight: 600;
}

.btn-buy-now:hover{
  background-color: #fc5858;
}

.btn-add-to-cart{
  border-style: solid;
  background-color: #ff9a00;
  border-color: transparent;
  border-radius: 4px;
  padding: 6px 30px;
  color: #fff;
  height: 44px;
  font-size: 20px;
  font-weight: 600;
}
.btn-add-to-cart:hover{
  background-color: #fca626;
}
</style>
