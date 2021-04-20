<script>
export default {
  data() {
    return {
      props: ['value', 'name'],

      form: {
        companyName: '',
        contactEmail: '',
        workPlace: '',
        tech: [],
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
  <b-container>
    <b-row align-v="center">
      <b-col cols="12" align="center">
        <b-card>
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

                <b-form-group label="Calisma Tipi:" label-for="workPlace">
                  <b-form-input
                    id="workPlace"
                    v-model="form.workPlace"
                    type="text"
                    placeholder="Remote/Istanbul"
                    required
                  ></b-form-input>
                </b-form-group>

                <b-form-group
                  label="Iletisim icin Email Adresi:"
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

                <b-form-group
                  id="tech"
                  v-slot="{ ariaDescribedby }"
                  label="Teknolojiler"
                >
                  <b-form-checkbox-group
                    id="tech"
                    v-model="form.tech"
                    :aria-describedby="ariaDescribedby"
                  >
                    <b-form-checkbox value="allTech.javascript"
                      >Javascript</b-form-checkbox
                    >
                    <b-form-checkbox value="that"
                      >Check that out</b-form-checkbox
                    >
                  </b-form-checkbox-group>
                </b-form-group>

                <b-button type="submit" variant="primary"
                  >Ilani Gonder</b-button
                >
              </b-form>
            </b-col>
          </b-row>
        </b-card>
      </b-col>
    </b-row>
  </b-container>
</template>

<style scoped>
.card {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}
</style>
