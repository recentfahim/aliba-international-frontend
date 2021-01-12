<template lang="html">
    <div class="table-repsonsive">
        <table class="table table-bordered">
            <thead>
                <tr>
                    <th scope="col">Order Number</th>
                    <th scope="col">Order Date</th>
                    <th scope="col">Amount</th>
                    <th scope="col">Payment Status</th>
                    <th scope="col">Order StatusStatus</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="item in tableData" :key="item.order_id">
                    <td>
                        <nuxt-link to="/account/invoice-detail">{{ item.order_id }}</nuxt-link>
                    </td>
                    <td>{{ item.order_date }}</td>
                    <td>{{ item.amount }}</td>
                    <td>
                      <span v-if="item.payment_status === 'Paid'" class="badge badge-pill badge-success">{{ item.payment_status }}</span>
                      <span v-else class="badge badge-pill badge-danger">{{ item.payment_status }}</span>
                    </td>
                    <td>
                      <span v-if="item.order_status === 'Delivered'" class="badge badge-pill badge-success">{{ item.order_status }}</span>
                      <span v-else-if="item.order_status === 'Canceled'" class="badge badge-pill badge-danger">{{ item.order_status }}</span>
                      <span v-else-if="item.order_status === 'Shipped'" class="badge badge-pill badge-primary">{{ item.order_status }}</span>
                      <span v-else-if="item.order_status === 'Processing'" class="badge badge-pill badge-info">{{ item.order_status }}</span>
                      <span v-else class="badge badge-pill badge-warning">{{ item.order_status }}</span>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    name: 'TableInvoices',
    data() {
        return {
            tableData: [
                {
                  order_id: '50',
                  order_date: '21-01-2021',
                  amount: '42.99',
                  payment_status: 'Paid',
                  order_status: 'Delivered'
                },
                {
                  order_id: '268',
                  order_date: '21-01-2021',
                  amount: '42.99',
                  payment_status: 'Paid',
                  order_status: 'Processing'
                },
                {
                  order_id: '522',
                  order_date: '21-01-2021',
                  amount: '42.99',
                  payment_status: 'Canceled',
                  order_status: 'Shipped'
                },
                {
                  order_id: '625',
                  order_date: '21-01-2021',
                  amount: '42.99',
                  payment_status: 'Canceled',
                  order_status: 'Shipping to Bangladesh'
                },
                {
                  order_id: '685',
                  order_date: '21-01-2021',
                  amount: '42.99',
                  payment_status: 'Paid',
                  order_status: 'Delivered'
                },
                {
                  order_id: '785',
                  order_date: '21-01-2021',
                  amount: '42.99',
                  payment_status: 'Canceled',
                  order_status: 'Canceled'
                },

            ]
        };
    }
};
</script>

<style lang="scss" scoped></style>
