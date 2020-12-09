<template>
  <div>
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
  </div>
</template>

<script>
import { required } from 'vuelidate/lib/validators';
import axios from 'axios';

export default {
  name: "SignIn",
  props: ['show_login_popup'],
  data() {
    return {
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
            localStorage.setItem('token', response.data.access_token)
            this.$store.dispatch('auth/setAuthStatus', true);
            this.show_login_popup = false
            this.$router.push('/');
          }
        });

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