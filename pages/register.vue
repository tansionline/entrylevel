<script>
export default {
  data() {
    return {
      email: '',
      password: '',
    }
  },
  methods: {
    async register() {
      try {
        await this.$fire.auth.createUserWithEmailAndPassword(
          this.email,
          this.password
        )
        this.$router.push('/login')
      } catch (e) {
        alert(e)
      }
    },
  },
}
</script>

<template>
  <b-container fluid>
    <b-row align-v="center" align-h="center" class="p-5">
      <b-col cols="6" align-self="center">
        <h2 align="center" class="mb-5">Create a account</h2>
        <b-form @submit.prevent="register">
          <b-form-group label="Email address:" label-for="email">
            <b-form-input
              v-model="email"
              type="email"
              name="email"
              placeholder="bugra@yildiz.com"
              required
            ></b-form-input>
          </b-form-group>

          <b-form-group label="Password:" label-for="password">
            <b-form-input
              v-model="password"
              type="password"
              name="password"
              placeholder="***********"
              required
            ></b-form-input>
          </b-form-group>
          <a href="/login">You have already account</a>

          <b-button
            class="btn btn-lg btn-block mt-4"
            variant="primary"
            type="submit"
            >Register</b-button
          >
        </b-form>
      </b-col>
    </b-row>
  </b-container>
</template>
