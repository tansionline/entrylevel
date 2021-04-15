<script>
export default {
  data() {
    return {
      email: '',
      password: '',
    }
  },
  methods: {
    async login() {
      try {
        await this.$fire.auth.signInWithEmailAndPassword(
          this.email,
          this.password
        )
        this.$router.push('/profile')
      } catch (e) {
        alert(e)
      }
    },
  },
}
</script>

<template>
  <div class="container-fluid">
    <div>
      <h1>Login</h1>
      <b-form @submit.prevent="login">
        <b-form-group label="Email address:" label-for="email">
          <b-form-input
            id="email"
            v-model="email"
            type="email"
            placeholder="cagatay@cali.com"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group label="Password:" label-for="password">
          <b-form-input
            v-model="password"
            placeholder="*******"
            type="password"
            required
          ></b-form-input>
        </b-form-group>
        <b-button type="submit" variant="primary">Login</b-button>
      </b-form>
    </div>
  </div>
</template>
