<template>
  <div>
    <div class="sign-in-up-container">
      <div>
        <div class="user-icon">
          <i class="fas fa-user-circle"></i>
        </div>
        <div class="welcome" v-if="!isLoggedIn">
          Welcome To Aliba International
        </div>
        <div v-else class="welcome">
          Hi, {{ user.name }}
        </div>
        <div class="button-container mt-6" v-if="!isLoggedIn">
          <v-row>
            <v-col md="6">
              <button class="btn btn-join" @click="showLoginPopup">Join</button>
            </v-col>
            <v-col md="6">
              <button class="btn btn-sign-in" @click="showLoginPopup">Sign In</button>
            </v-col>
          </v-row>
        </div>
        <div class="button-container mt-6" v-else>
          <v-row>
            <v-col md="12">
              <button class="btn btn-logout" @click.prevent="handleLogout">Log Out</button>
            </v-col>
          </v-row>
        </div>
      </div>
    </div>
    <div class="clearfix"></div>

    <!--- Login SignUp popup -->
    <vodal :show="show_login_popup" animation="rotate" @hide="show_login_popup = false" :height="550">
      <div>
        <div class="text-center">
          <img src="/img/aliba_logo.jpeg" width="25%" alt="Aliba International" />
        </div>
        <div class="mt-3">
          <v-tabs centered>
            <v-tabs-slider color="red"></v-tabs-slider>

            <v-tab href="#signin">
              Sign In
            </v-tab>

            <v-tab href="#join">
              Join
            </v-tab>

            <v-tab-item key="signin" id="signin" class="mt-4">
              <SignIn @hideLoginPopup="hideLoginPopup"></SignIn>
            </v-tab-item>
            <v-tab-item key="join" id="join" class="mt-4">
              <SignUp @hideLoginPopup="hideLoginPopup"></SignUp>
            </v-tab-item>
          </v-tabs>
        </div>

      </div>
    </vodal>
  </div>
</template>

<script>
import vodal from 'vodal';
import { required } from 'vuelidate/lib/validators';
import axios from 'axios';
import SignIn from '~/components/home/account/SignIn';
import SignUp from '~/components/home/account/SignUp';
import { mapState } from 'vuex';

export default {
  name: 'SignInSignUp',
  components: {
    vodal,
    SignIn,
    SignUp
  },

  data() {
    return {
      show_login_popup: false,
      user: null
    };
  },

  computed: {
    ...mapState({
      isLoggedIn: state => state.auth.isLoggedIn
    })
  },

  created() {
    this.user = JSON.parse(localStorage.getItem('auth_user'))
  },

  methods: {
    showLoginPopup() {
      this.show_login_popup = true;
    },

    hideLoginPopup() {
      this.show_login_popup = false;
    },

    handleLogout(){
      this.$store.dispatch('auth/setAuthStatus', false);
      localStorage.removeItem('auth_user')
      localStorage.removeItem('token')
    }
  }
};
</script>

<style scoped>
.sign-in-up-container {
  background: rgb(255, 245, 245);
  height: 275px;
  border-radius: 10px;
  text-align: center;
}

.user-icon {
  font-size: 60px;
  color: #fb7a3f;
}

.welcome {
  font-size: 14px;
  color: #000;
  height: 18px;
  overflow: hidden;
  line-height: 18px;
  margin-bottom: 0;
  font-weight: 900;
  font-family: OpenSans-Extrabold, Open Sans, Arial, Helvetica, sans-serif, SimSun;
}

.btn-join {
  width: 80px;
  font-size: 13px;
  color: #fff;
  background-color: #ff4747;
  border-radius: 15px;
  padding: 6px 0;
  float: right;
}
.btn-logout {
  width: 80px;
  font-size: 13px;
  color: #fff;
  background-color: #ff4747;
  border-radius: 15px;
  padding: 6px 0;
}

.btn-sign-in {
  width: 80px;
  font-size: 13px;
  color: #fff;
  background-color: #00a040;
  border-radius: 15px;
  padding: 6px 0;
  float: left;
}

.btn-join:hover {
  background-color: #ff5050;
}
.btn-logout:hover {
  background-color: #ff5050;
}

.btn-sign-in {
  width: 80px;
  font-size: 13px;
  color: #fff;
  background-color: #00a040;
  border-radius: 15px;
  padding: 6px 0;
  float: left;
}

.btn-sign-in:hover {
  background-color: #00c64f;
}

input {
  border-radius: 5px;
}
</style>