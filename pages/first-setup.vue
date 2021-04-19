<script>
export default {
  data() {
    return {
      form: {
        companyName: '',
        contactEmail: '',
        workPlace: [],
        checked: [],
      },
    }
  },
  methods: {
    onSubmit() {
      console.log('sended')
    },
  },
}
</script>

<template>
  <b-container fluid>
    <b-row align-v="center">
      <b-col cols="12" align="center">
        <div class="card">
          <b-row>
            <b-col>
              <h1>İlan Paylaş</h1>
            </b-col>
          </b-row>
          <b-row>
            <b-col>
              <b-form @submit.prevent="onSubmit">
                <b-form-group label="Sirket Ismi:" label-for="companyName">
                  <b-form-input
                    id="companyName"
                    v-model="form.companyName"
                    type="text"
                    placeholder="Trendyol"
                    required
                  ></b-form-input>
                </b-form-group>

                <b-form-group
                  label="Iletisim Email Adresi:"
                  label-for="contactEmail"
                >
                  <b-form-input
                    id="contactEmail"
                    v-model="form.contactEmail"
                    type="email"
                    placeholder="selam@trendyol.com"
                    required
                  ></b-form-input>
                </b-form-group>

                <b-form-group id="input-group-4" v-slot="{ ariaDescribedby }">
                  <b-form-checkbox-group
                    id="checkboxes-4"
                    v-model="form.checked"
                    :aria-describedby="ariaDescribedby"
                  >
                    <b-form-checkbox value="me">Check me out</b-form-checkbox>
                    <b-form-checkbox value="that"
                      >Check that out</b-form-checkbox
                    >
                  </b-form-checkbox-group>
                </b-form-group>

                <b-button type="submit" variant="primary">Submit</b-button>
              </b-form>
            </b-col>
          </b-row>
        </div>
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
