<template lang="html">
    <section class="ps-my-account ps-page--account">
        <div class="container">
            <div class="row">
                <div class="col-lg-4">
                    <div class="ps-section__left">
                        <aside class="ps-widget--account-dashboard">
                            <div class="ps-widget__header">
                                <img src="/img/users/3.jpg" />
                                <figure>
                                    <figcaption>Hello</figcaption>
                                    <p>username@gmail.com</p>
                                </figure>
                            </div>
                            <div class="ps-widget__content">
                                <AccountLinks :links="links" />
                            </div>
                        </aside>
                    </div>
                </div>
                <div class="col-lg-8">
                    <div class="ps-section--account-setting">
                        <div class="ps-section__header">
                            <h3>
                                Order No: #854 -
                                <strong>Delivered</strong>
                            </h3>
                        </div>
                        <div class="ps-section__content">
                            <div class="row">
                                <div class="col-md-4 col-12">
                                    <figure class="ps-block--invoice">
                                        <figcaption>
                                            Address
                                        </figcaption>
                                        <div class="ps-block__content">
                                            <strong>
                                                User Name
                                            </strong>
                                            <p>
                                                Address: Banani, Dhaka-1213
                                            </p>
                                            <p>
                                                Phone: 016582156142
                                            </p>
                                        </div>
                                    </figure>
                                </div>
                                <div class="col-md-4 col-12">
                                    <figure class="ps-block--invoice">
                                        <figcaption>
                                            Shipping Fee
                                        </figcaption>
                                        <div class="ps-block__content">
                                            <p>
                                                Shipping Fee: 100
                                            </p>
                                        </div>
                                    </figure>
                                </div>
                                <div class="col-md-4 col-12">
                                    <figure class="ps-block--invoice">
                                        <figcaption>
                                            Payment
                                        </figcaption>
                                        <div class="ps-block__content">
                                            <p>
                                                Payment Method: Visa
                                            </p>
                                        </div>
                                    </figure>
                                </div>
                            </div>
                            <div class="table-responsive">
                                <TableInvoice :products="invoiceProducts" />
                            </div>
                            <nuxt-link to="/account/invoices">
                                <a class="ps-btn ps-btn--sm ">
                                    Back to orders
                                </a>
                            </nuxt-link>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import AccountLinks from './modules/AccountLinks';
import TableInvoice from './modules/TableInvoice';
export default {
    name: 'InvoiceDetail',
    components: { TableInvoice, AccountLinks },
    data() {
        return {
          links: [
            {
              text: 'Account Information',
              url: '/account/my-profile',
              icon: 'icon-user'
            },
            {
              text: 'Orders',
              url: '/account/orders',
              icon: 'icon-store',
              active: true
            },
            {
              text: 'Address',
              url: '/account/addresses',
              icon: 'icon-map-marker'
            }
          ],
            invoiceProducts: [
                {
                    id: '6',
                    thumbnail: '/img/products/shop/5.jpg',
                    title: 'Grand Slam Indoor Of Show Jumping Novel',
                    vendor: "Robert's Store",
                    sale: true,
                    price: '32.99',
                    sale_price: '41.00',
                    rating: true,
                    ratingCount: '4',
                    badge: [
                        {
                            type: 'sale',
                            value: '-37%'
                        }
                    ]
                },
                {
                    id: '7',
                    thumbnail: '/img/products/shop/6.jpg',
                    title: 'Sound Intone I65 Earphone White Version',
                    vendor: 'Youngshop',
                    sale: true,
                    price: '100.99',
                    sale_price: '106.00',
                    rating: true,
                    ratingCount: '5',
                    badge: [
                        {
                            type: 'sale',
                            value: '-5%'
                        }
                    ]
                }
            ]
        };
    }
};
</script>

<style lang="scss" scoped>
.ps-section--account-setting{
  background-color: white;
  padding: 20px;
  border-radius: 10px;
}
.ps-my-account{
  padding-top: 30px;
}
.ps-section__left{
  background-color: white;
  padding: 20px;
  border-radius: 10px;
}
.ps-section__content{
  border-radius: 10px;
}
</style>
