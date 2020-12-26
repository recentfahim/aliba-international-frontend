<template>
  <div class="checkout-page pb-5">
    <v-container>
      <v-row class="pt-5">
        <v-col md="8">
          <v-row>
            <v-col md="12" class="checkout-info">
              <div class="checkout-info-item">
                <div>
                  <span class="checkout-info-item-title">Shipping Information</span>
                </div>
                <div class="mt-5">
                  <ul class="address-container">
                    <li v-for="user_address in user_addresses" class="address-item mt-2" v-bind:class="{ active: selected_user_address === user_address}" @click="selected_address(user_address)">
                      <div>
                        <span class="address-item-name">{{ user_address.name }}</span>
                      </div>
                      <div>
                        <span class="address-item-address">{{ user_address.address}}</span>
                      </div>
                    </li>
                  </ul>
                </div>
                <div class="mt-5">
                  <span class="new-address" @click="showAddressPopup">+ Add new address</span>
                </div>
              </div>
            </v-col>
            <v-col md="12" class="checkout-info mt-5">
              <div class="checkout-info-item">
                <div>
                  <span class="checkout-info-item-title">Payment Methods</span>
                </div>
                <div class="mt-5">
                  <img src="~/static/img/payment-method/pay-with.png" alt="pay with">
                </div>
              </div>
            </v-col>
            <v-col md="12" class="checkout-info mt-5">
              <div class="checkout-info-item">
                <div class="mb-3">
                  <span class="checkout-info-item-title">Order Review</span>
                </div>
                <div class="product-list">
                  <v-row>
                    <v-col md="3">
                      <img src="https://ae01.alicdn.com/kf/H8d4d94cb140c4fedb07768d3b276d9559/Polarized-Sunglasses-Men-Movement-Designer-Driving-Sun-glasses-Women-Vintage-Anti-UV-Driver-Black-Goggles-Eyewear.jpg">
                    </v-col>
                    <v-col md="6">
                      <div class="product-name">
                        Polarized Sunglasses Men Movement Designer Driving Sun glasses Women Vintage Anti-UV Driver Black Goggles Eyewear Gafas de sol
                      </div>
                      <div class="product-price">
                        BDT 305
                      </div>
                    </v-col>
                    <v-col md="3">
                      <div class="d-flex float-right">
                        <div>
                          <i class="fas fa-minus-circle quantity-icon"></i>
                        </div>
                        <div class="ml-4 mr-4 quantity">
                          <span>2</span>
                        </div>
                        <div>
                          <i class="fas fa-plus-circle quantity-icon"></i>
                        </div>
                      </div>
                    </v-col>
                  </v-row>
                </div>
                <div class="mt-4 price-summary">
                  <v-row>
                    <v-col md="8"></v-col>
                    <v-col md="4">
                      <v-row>
                        <v-col md="6">
                          Subtotal
                        </v-col>
                        <v-col md="6">
                          <span class="float-right">BDT 507</span>
                        </v-col>
                        <v-col md="6">
                          Shipping
                        </v-col>
                        <v-col md="6">
                          <span class="float-right">BDT 100</span>
                        </v-col>
                        <v-col md="6" class="mt-3 total-pay">
                          Total
                        </v-col>
                        <v-col md="6" class="mt-3 total-pay">
                          <span class="float-right">BDT 607</span>
                        </v-col>
                      </v-row>
                    </v-col>
                  </v-row>
                </div>
              </div>
            </v-col>
          </v-row>
        </v-col>
        <v-col md="4">
          <div class="order-summary">
            <div class="mb-5">
              <span class="order-summary-title">Order Summary</span>
            </div>
            <div>
              <v-row>
                <v-col md="5">
                  <span class="total">Total</span>
                </v-col>
                <v-col md="7">
                  <span class="total-amount">BDT 305</span>
                </v-col>
              </v-row>
            </div>
            <div class="mt-5 mb-5">
              <button class="btn w-100 place-order-btn">Place Order</button>
            </div>
          </div>
        </v-col>
      </v-row>
    </v-container>
    <vodal :show="show_address_popup" animation="rotate" @hide="show_address_popup = false" :height="450" :width="900">
      <div class="m-4">
        <div>
          <span class="new-address-popup-title">Select other addresses</span>
        </div>
        <div class="mt-5">
          <v-row>
            <v-col md="12" class="mb-3">
              <span class="address-text">Contact</span>
            </v-col>
            <v-col md="6">
              <v-text-field
                  placeholder="Name"
                  v-model="name"
                  class="ps-text-field"
                  outlined>
              </v-text-field>
            </v-col>
            <v-col md="6">
              <v-text-field
                  placeholder="Mobile Number"
                  v-model="mobile_number"
                  class="ps-text-field"
                  outlined>
              </v-text-field>
            </v-col>
            <v-col md="12" class="mb-3">
              <span class="address-text">Address</span>
            </v-col>
            <v-col md="6">
              <v-select v-if="locations"
                  :items="locations"
                  item-text="name"
                  item-value="id"
                  label="City"
                  class="ps-text-field"
                  v-model="location"
                  dense
                  outlined
              ></v-select>
            </v-col>
            <v-col md="6">
              <v-select v-if="areas"
                        :items="areas"
                        item-text="name"
                        item-value="id"
                        label="Area"
                        class="ps-text-field"
                        v-model="area"
                        dense
                        outlined
              ></v-select>
            </v-col>
            <v-col md="12">
              <v-text-field
                  placeholder="Address"
                  v-model="address"
                  class="ps-text-field"
                  outlined>
              </v-text-field>
            </v-col>
            <v-col md="12" v-if="btn_loading">
              <button class="btn btn-danger btn-lg w-25 btn-save" disabled>
                <span class="spinner-border spinner-border-sm" role="status" aria-hidden="true"></span>
                  Saving
              </button>
            </v-col>
            <v-col md="12" v-else>
              <button class="btn btn-danger btn-lg w-25 btn-save" @click="saveAddress">
                Save and Continue
              </button>
            </v-col>

          </v-row>
        </div>
      </div>
    </vodal>
  </div>
</template>

<script>
import vodal from 'vodal';
import axios from 'axios';

export default {
  name: 'Checkout',
  layout: 'layout-default',
  components: {
    vodal
  },
  data(){
    return{
      show_address_popup: false,
      user_addresses: null,
      locations: null,
      areas: null,
      area: null,
      location: null,
      name: null,
      address: null,
      mobile_number: null,
      btn_loading: false,
      selected_user_address: ''
    }
  },
  created() {
    axios.get(process.env.baseURL + `cities`).then((response) => {
      this.locations = response.data.data
    })
    const headers = {
      'Content-Type': 'application/json',
      'Authorization': 'Bearer '+ localStorage.getItem('token')
    }
    axios.get(process.env.baseURL + `user-address`, {headers: headers}).then((response) => {
      this.user_addresses = response.data.data
    })

  },
  watch: {
    location () {
      axios.get(process.env.baseURL + "areas/"+ this.location).then((response) => {
        this.areas = response.data.data
      })
    }
  },
  methods: {
    showAddressPopup(){
      this.show_address_popup = true
    },

    selected_address(user_address){
      this.selected_user_address = user_address
    },

    saveAddress(){
      this.btn_loading = true
      const headers = {
        'Content-Type': 'application/json',
        'Authorization': 'Bearer '+ localStorage.getItem('token')
      }
      let data = {
        'address_name': this.name,
        'address_mobile_number': this.mobile_number,
        'address_location': this.location,
        'address_area': this.area,
        'address': this.address
      }
      axios.post(process.env.baseURL + `save-address`, data, { headers: headers })
        .then((response) => {
          if(response.data.success) {
            this.btn_loading = false
            this.show_address_popup = false
            this.$notify(
                {
                  group: 'addCartSuccess',
                  type: 'warn',
                  title: 'Error!',
                  text: response.data.message
                }
            )
          }
          else{
            this.$notify(
                {
                  group: 'addCartSuccess',
                  type: 'warn',
                  title: 'Error!',
                  text: response.data.message
                }
            )
            return;
          }
        })
    },
  }
};
</script>

<style scoped>
.checkout-page{
  background-color: #f2f2f2;
}
.checkout-info{
  background-color: #ffffff;
  border-radius: 10px;
}
.checkout-info-item{
  margin: 20px;
  font-family: Open Sans,Arial,Helvetica,sans-serif,Heiti;
}
.checkout-info-item-title{
  font-family: Open Sans,Arial,Helvetica,sans-serif,Heiti;
  font-size: 18px;
  color: #000;
  font-weight: 700;
  margin-bottom: 24px;
  margin-top: 8px;
  line-height: 25px;
}
.order-summary{
  background-color: #ffffff;
  border-radius: 10px;
  padding: 20px;
}
.order-summary-title{
  font-family: Open Sans,Arial,Helvetica,sans-serif,Heiti;
  font-size: 20px;
  font-weight: 700;
}
.total-amount{
  font-family: Open Sans,Arial,Helvetica,sans-serif,Heiti;
  font-size: 20px;
  font-weight: 700;
  float: right;
}
.total{
  font-family: Open Sans,Arial,Helvetica,sans-serif,Heiti;
  font-size: 15px;
  font-weight: 700;
  float: left;
}
.place-order-btn{
  font-family: Open Sans,Arial,Helvetica,sans-serif,Heiti;
  font-size: 18px;
  background-color: #ff5959;
  border-color: #ff5959;
  color: #ffffff;
  line-height: 30px;
}
.place-order-btn:hover{
  background-color: #fa6767;
  border-color: #fa6767;
}
.new-address{
  color: #2e9cc3;
  font-size: 12px;
  font-weight: 600;
  cursor: pointer;
}
.btn-save{
  height: 50px;
  font-size: 15px;
}
.address-text{
  font-size: 15px;
  font-family: Open Sans,Arial,Helvetica,sans-serif,Heiti;
  font-weight: 700;
}
.new-address-popup-title{
  font-family: Open Sans,Arial,Helvetica,sans-serif,Heiti;
  font-size: 25px;
  font-weight: 700;
}
.quantity-icon{
  font-size: 25px;
  color: #797979;
}
.quantity{
  font-family: Open Sans,Arial,Helvetica,sans-serif,Heiti;
  font-size: 20px;
  margin-top: -3px;
}
.product-price{
  font-size: 18px;
  font-weight: 700;
  font-family: Open Sans,Arial,Helvetica,sans-serif,Heiti;
  margin-top: 15px;
}
.product-list{
  border-bottom: 1px solid #d2d2d2;
  padding-bottom: 15px;
}
.price-summary{
  font-size: 14px;
  font-family: Open Sans,Arial,Helvetica,sans-serif,Heiti;
  color: #797979;
}
.total-pay{
  color: #000000;
}
.address-item{
  border-radius: 5px;
  box-shadow: 0 0 6px 0 rgba(0,0,0,.16);
  background-color: #fff;
  padding: 16px 20px;
  min-height: 67px;
}
.address-container{
  list-style-type: none;
}
.address-item-name{
  font-family: Open Sans,Arial,Helvetica,sans-serif,Heiti;
  font-size: 14px;
  font-weight: 700;
}
.address-item-address{
  font-family: Open Sans,Arial,Helvetica,sans-serif,Heiti;
  font-size: 12px;
}
.active{
  background: #ebfaf8;
}
</style>