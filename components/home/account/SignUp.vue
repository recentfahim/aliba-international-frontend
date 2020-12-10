<template>
  <div>
    <div class="form-group mb-0">
      <v-text-field
          v-model="user_name"
          :error-messages="nameErrors"
          @input="$v.user_name.$touch()"
          placeholder="Name"
          height="50"
          outlined
      />
    </div>
    <div class="form-group mb-0">
      <v-text-field
          v-model="email"
          type="email"
          :error-messages="emailErrors"
          @input="$v.email.$touch()"
          placeholder="Email"
          height="50"
          outlined
      />
    </div>
    <div class="form-group mb-0">
      <v-text-field
          v-model="password"
          type="password"
          :error-messages="passwordErrors"
          @input="$v.password.$touch()"
          placeholder="Password"
          height="50"
          outlined
      />
    </div>
    <div class="form-group mb-0">
      <v-text-field
          v-model="confirm_password"
          type="password"
          :error-messages="confirmPasswordErrors"
          @input="$v.confirm_password.$touch()"
          placeholder="Confirm Password"
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
        Create Account
      </button>
    </div>
  </div>
</template>

<script>
import { required } from 'vuelidate/lib/validators';
import axios from 'axios';

export default {
  name: "SignUp",
  props: ['show_login_popup'],
  data() {
    return {
      user_name: null,
      email: null,
      password: null,
      confirm_password: null
    };
  },
  computed: {
    emailErrors() {
      const errors = [];
      if (!this.$v.email.$dirty) return errors;
      !this.$v.email.required && errors.push('This field is required');
      return errors;
    },
    nameErrors() {
      const errors = [];
      if (!this.$v.user_name.$dirty) return errors;
      !this.$v.user_name.required && errors.push('This field is required');
      return errors;
    },
    passwordErrors() {
      const errors = [];
      if (!this.$v.password.$dirty) return errors;
      !this.$v.password.required && errors.push('This field is required');
      return errors;
    },
    confirmPasswordErrors() {
      const errors = [];
      if (!this.$v.confirm_password.$dirty) return errors;
      !this.$v.confirm_password.required && errors.push('This field is required');
      return errors;
    }
  },
  validations: {
    email: { required },
    user_name: { required },
    password: { required },
    confirm_password: { required }
  },
  methods: {
    handleSubmit() {
      if(this.password === this.confirm_password) {
        this.$v.$touch();
        if (!this.$v.$invalid) {
          axios.post(process.env.baseURL + `register`,
              {
                'name': this.user_name,
                'email': this.email,
                'password': this.password,
                'password_confirmation': this.confirm_password
              }).then((response) => {
            if (response.data.message) {
              this.$notify(
                  {
                    group: 'addCartSuccess',
                    type: 'warn',
                    title: 'Error!',
                    text: response.data.message.message
                  }
              )
              return;
            } else {
              localStorage.setItem('auth_user', JSON.stringify(response.data))
              localStorage.setItem('token', response.data.access_token)
              this.$store.dispatch('auth/setAuthStatus', true);
              this.show_login_popup = false
              this.$router.push('/');
            }
          });
        }
      }
      else{
        this.$notify(
            {
              group: 'addCartSuccess',
              type: 'warn',
              title: 'Error!',
              text: `Password did not match`
            }
        )
      }
    }
  }
}
</script>

<style scoped>
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