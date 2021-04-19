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
  <div class="container-fluid">
    <div class="card" v-on:click="hr">
      <div class="container">
        <h4>I Am HR</h4>
      </div>
    </div>
    <div class="card" v-on:click="employe">
      <div class="container">
        <h4>I Am Employe</h4>
      </div>
    </div>
  </div>
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

.container {
  display: flex;

  padding: 2px 16px;
}
</style>
