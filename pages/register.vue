<script>
export default {
  data() {
    return {
      email: '',
      password: '',
    }
  },
  methods: {
    async createUser() {
      try {
        await this.$fire.auth.createUserWithEmailAndPassword(
          this.email,
          this.password
        )
        console.log('Yaay')
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
      <b-form @submit.prevent="createUser">
        <b-form-group
          label="Email address:"
          label-for="email"
          description="asd."
        >
          <b-form-input
            id="email"
            v-model="email"
            type="email"
            placeholder="cagatay@cali.com"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group label="Your Name:" label-for="password">
          <b-form-input
            v-model="password"
            placeholder="*******"
            type="password"
            required
          ></b-form-input>
        </b-form-group>
        <b-button type="submit" variant="primary">Register</b-button>
      </b-form>
    </div>
  </div>
</template>
