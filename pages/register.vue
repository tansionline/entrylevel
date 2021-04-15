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
  <div class="container-fluid">
    <div class="container">
      <div class="register-card">
        <h1>Register</h1>
        <form>
          <label for="email">Email:</label>
          <input
            type="email"
            v-model="email"
            name="email"
            placeholder="cagatay@cali.com"
          />

          <label for="password">Password:</label>
          <input
            type="password"
            v-model="password"
            name="password"
            placeholder="***********"
          />
          <a href="/login">Have you account</a>
          <input type="submit" value="Submit" />
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
input[type='email'],
input[type='password'] {
  width: 100%;
  padding: 0.5em 1.5em;
  margin: 0.4em;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

input[type='submit'] {
  width: 100%;
  background-color: #4caf50;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  border-radius: 0.2em;
  cursor: pointer;
}

input[type='submit']:hover {
  background-color: #45a049;
}

div {
  border-radius: 5px;
  padding: 20px;
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
