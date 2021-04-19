<script>
export default {
  data() {
    return {}
  },
  methods: {
    hr() {
      this.$router.push('/hr')
    },
    employe() {
      this.$router.push('/employe')
    },
  },
}
</script>

<template>
  <b-container fluid>
    <b-row align-v="center">
      <b-col cols="6">
        <div class="card">
          <h1>Hello</h1>
        </div>
      </b-col>
      <b-col cols="6">
        <h1>Hello</h1>
      </b-col>
    </b-row>
  </b-container>
</template>

<style scoped>
.card {
  padding: 1rem;
  align-items: center;
  justify-content: center;

  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  width: 40%;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}
</style>
