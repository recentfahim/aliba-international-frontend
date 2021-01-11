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
                                <AccountLinks />
                            </div>
                        </aside>
                    </div>
                </div>
                <div class="col-lg-8">
                    <div class="ps-section--account-setting">
                        <div class="ps-section__content">
                            <div>
                                <figure class="ps-block--address">
                                    <figcaption>
                                        Addresses
                                    </figcaption>
                                    <div class="ps-block__content">
                                      <div v-if="user_addresses">
                                        <ul class="address-container">
                                          <li v-for="user_address in user_addresses" class="address-item mt-2">
                                            <div>
                                              <span class="address-item-name">{{ user_address.name }}</span>
                                            </div>
                                            <div>
                                              <span class="address-item-address">{{ user_address.address}}</span>
                                            </div>
                                          </li>
                                        </ul>
                                      </div>
                                      <div v-else>
                                        <p>
                                            You have not set up any address yet.
                                        </p>
                                      </div>
                                      <div>
                                        <button class="btn btn-danger btn-lg w-25 btn-add-address" @click="showAddressPopup">
                                          <i class="fas fa-plus"></i> Add New
                                        </button>
                                      </div>
                                    </div>
                                </figure>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
        </div>
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
    </section>

</template>

<script>
import AccountLinks from './modules/AccountLinks';
import axios from 'axios';
import vodal from 'vodal';

export default {
    name: 'Addresses',
    components: { AccountLinks , vodal},
    data() {
        return {
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
        };
    },
  methods: {
    showAddressPopup(){
      this.show_address_popup = true
    },
    getAddress(){
      const headers = {
        'Content-Type': 'application/json',
        'Authorization': 'Bearer '+ localStorage.getItem('token')
      }
      axios.get(process.env.baseURL + `user-address`, {headers: headers}).then((response) => {
        this.user_addresses = response.data.data
        console.log(this.user_addresses)
      })
    },
    getLocations(){
      axios.get(process.env.baseURL + `cities`).then((response) => {
        this.locations = response.data.data
      })
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
              axios.get(process.env.baseURL + `user-address`, {headers: headers}).then((response) => {
                this.user_addresses = response.data.data
              })
              this.show_address_popup = false
              this.$notify(
                  {
                    group: 'addCartSuccess',
                    type: 'success',
                    title: 'Successful!',
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
  },

  created() {
    this.getAddress();
    this.getLocations();
  },
  watch: {
    location () {
      axios.get(process.env.baseURL + "areas/"+ this.location).then((response) => {
        this.areas = response.data.data
      })
    }
  },
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
.btn-add-address{
  font-family: Open Sans,Arial,Helvetica,sans-serif,Heiti;
  font-size: 18px;
  background-color: #ff5959;
  border-color: #ff5959;
  color: #ffffff;
  line-height: 30px;
}
.btn-add-address:hover{
  background-color: #fa6767;
  border-color: #fa6767;
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
</style>
