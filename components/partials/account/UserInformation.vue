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
                    <section class="ps-section--account-setting">
                        <div class="ps-section__content">
                          <div>
                            <figure class="ps-block--address">
                              <figcaption>
                                Profile
                              </figcaption>
                              <div class="ps-block__content">
                                <div class="text-center mb-4">
                                  <img src="/img/users/no_user.png" width="150">
                                </div>
                                <div>
                                  <v-row>
                                    <v-col md="6">
                                      <span class="address-text">Email</span>
                                      <v-text-field
                                          placeholder="Email"
                                          v-model="email"
                                          class="ps-text-field mt-2"
                                          outlined
                                          :disabled="edit_enable === false">
                                      </v-text-field>
                                    </v-col>
                                    <v-col md="6">
                                      <span class="address-text">Name</span>
                                      <v-text-field
                                          placeholder="Name"
                                          v-model="name"
                                          class="ps-text-field mt-2"
                                          outlined
                                          :disabled="edit_enable === false">
                                      </v-text-field>
                                    </v-col>
                                    <v-col md="6">
                                      <span class="address-text">Mobile Number</span>
                                      <v-text-field
                                          placeholder="Mobile Number"
                                          v-model="mobile_number"
                                          class="ps-text-field mt-2"
                                          prefix="+88"
                                          outlined
                                          :disabled="edit_enable === false">
                                      </v-text-field>
                                    </v-col>
                                    <v-col md="6">
                                      <span class="address-text">Sex</span>
                                      <v-select
                                          :items="['Male', 'Female']"
                                          label="Sex"
                                          v-model="sex"
                                          class="ps-text-field mt-2"
                                          dense
                                          outlined
                                          :disabled="edit_enable === false"></v-select>
                                    </v-col>
                                    <div>
                                      <v-btn
                                          depressed
                                          color="error"
                                          large
                                          @click="editEnabled"
                                      >
                                        Edit
                                      </v-btn>
                                    </div>
                                  </v-row>
                                </div>

                              </div>
                            </figure>
                          </div>
                        </div>
                    </section>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import AccountLinks from './modules/AccountLinks';
import axios from 'axios';
export default {
    name: 'UserInformation',
    components: { AccountLinks },
    data() {
        return {
          user_data: null,
          name: null,
          sex: null,
          mobile_number: null,
          email: null,
          edit_enable: false
        };
    },
    methods: {
      getUser(){
        const headers = {
          'Content-Type': 'application/json',
          'Authorization': 'Bearer '+ localStorage.getItem('token')
        }
        axios.get(process.env.baseURL + `users`, {headers: headers} ).then((response) => {
          this.user_data = response.data
        })
      },
      editEnabled(){
        this.edit_enable = true
      }
    },
    mounted() {
      this.getUser()
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
</style>
