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
                    <div class="ps-page__content">
                        <div class="ps-section--account-setting">
                            <div class="ps-section__header">
                                <h3>Orders</h3>
                            </div>
                            <div class="ps-section__content">
                                <TableInvoices />
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import AccountLinks from './modules/AccountLinks';
import TableInvoices from './modules/TableInvoices';

export default {
    name: 'OrderDetail',
    components: { TableInvoices, AccountLinks },
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
          ]
        };
    }
};
</script>

<style lang="scss" scoped>
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
.ps-page__content{
  background-color: white;
  padding: 20px;
  border-radius: 10px;
}
</style>
