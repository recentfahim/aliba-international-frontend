<template>
  <div>
    <div class="sign-in-up-container">
      <div>
        <div class="user-icon">
          <i class="fas fa-user-circle"></i>
        </div>
        <div class="welcome">
          Welcome To Aliba International
        </div>
        <div class="button-container mt-6">
          <v-row>
            <v-col md="6">
              <button class="btn btn-join" @click="showLoginPopup">Join</button>
            </v-col>
            <v-col md="6">
              <button class="btn btn-sign-in" @click="showLoginPopup">Sign In</button>
            </v-col>
          </v-row>
        </div>
      </div>
    </div>
    <div class="clearfix"></div>

    <!--- Login SignUp popup -->
    <vodal :show="show" animation="rotate" @hide="show = false" height=450>
      <div>
        <div class="text-center">
          <img src="/img/aliba_logo.jpeg" width="25%" alt="Aliba International" />
        </div>
        <div class="mt-3">
          <v-tabs v-model="tab" align-with-title centered>
            <v-tabs-slider color="red"></v-tabs-slider>

            <v-tab href="#signin">
              Sign In
            </v-tab>

            <v-tab href="#join">
              Join
            </v-tab>

            <v-tab-item key="signin" id="signin" class="mt-4">
              <div class="form-group mb-0">
                  <v-text-field
                      v-model="username"
                      class="ps-text-field"
                      :error-messages="usernameErrors"
                      @input="$v.username.$touch()"
                      placeholder="Email"
                      height="50"
                      outlined
                  />
              </div>
              <div class="form-group mb-0">
                <v-text-field
                    v-model="password"
                    type="password"
                    class="ps-text-field"
                    :error-messages="passwordErrors"
                    @input="$v.password.$touch()"
                    placeholder="Password"
                    height="50"
                    outlined
                />
              </div>
              <div class="form-group submit">
                <button
                    type="submit"
                    class="ps-btn ps-btn--fullwidth button-sign w-100"
                    @click.prevent="handleSubmit"
                >
                  Sign In
                </button>
              </div>

            </v-tab-item>
            <v-tab-item key="join" id="join" class="mt-4">
              <div class="form-group mb-0">
                <v-text-field
                    v-model="username"
                    class="ps-text-field"
                    :error-messages="usernameErrors"
                    @input="$v.username.$touch()"
                    placeholder="Email"
                    height="50"
                    outlined
                />
              </div>
              <div class="form-group mb-0">
                <v-text-field
                    v-model="password"
                    type="password"
                    class="ps-text-field"
                    :error-messages="passwordErrors"
                    @input="$v.password.$touch()"
                    placeholder="Password"
                    height="50"
                    outlined
                />
              </div>
              <div class="form-group">
                <input type="text" class="form-control form-control-sm" placeholder="Username">
              </div>
              <div class="form-group">
                <input type="password" class="form-control form-control-sm" placeholder="Password">
              </div>
              <div class="form-group">
                <input type="password" class="form-control form-control-sm" placeholder="Confirm Password">
              </div>
              <div class="form-group">
                <button type="button" class="button-sign w-100">Create Account</button>
              </div>
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

export default {
  name: 'SignInSignUp',
  components: {
    vodal
  },
  data() {
    return {
      show: false,
      username: null,
      password: null
    };
  },
  computed: {
    usernameErrors() {
      const errors = [];
      if (!this.$v.username.$dirty) return errors;
      !this.$v.username.required && errors.push('This field is required');
      return errors;
    },
    passwordErrors() {
      const errors = [];
      if (!this.$v.password.$dirty) return errors;
      !this.$v.password.required && errors.push('This field is required');
      return errors;
    }
  },

  validations: {
    username: { required },
    password: { required }
  },

  methods: {
    showLoginPopup() {
      this.show = true;
    },
    handleSubmit() {
      this.$v.$touch();
      if (!this.$v.$invalid) {
        axios.post(`http://127.0.0.1:8000/api/login`,
            {
              'email': this.username,
              'password': this.password
            }).then((response) => {
          if (response.data.message) {
            console.log(response.data.message);
            return;
          } else {
            localStorage.setItem('auth_user', JSON.stringify(response.data))
            localStorage.setItem('token', response.data.token)
            this.$store.dispatch('auth/setAuthStatus', true);
            this.show = false
            this.$router.push('/');
          }
        });

      }
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

.button-sign {
  height: 50px;
  background-color: #ff4747;
  font-size: 20px;
  font-weight: 600;
  border-radius: 5px;
  color: #ffffff;
  text-transform: uppercase;
}
</style>