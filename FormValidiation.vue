<template>
    <v-container>
      <v-form v-model="isValid" ref="form">
        <v-text-field
          v-model="form.name"
          label="Adınız"
          :rules="[v => !!v || 'Ad zorunludur']"
          required
        ></v-text-field>
        <v-text-field
          v-model="form.email"
          label="Email"
          :rules="[v => !!v || 'Email zorunludur', v => /.+@.+\..+/.test(v) || 'Geçerli bir email girin']"
          required
        ></v-text-field>
        <v-select
          v-model="form.country"
          :items="countries"
          label="Ülke Seçin"
          :rules="[v => !!v || 'Ülke seçimi zorunludur']"
          required
        ></v-select>
  
        <!-- Checkbox -->
        <v-checkbox
          v-model="form.agree"
          label="Şartları kabul ediyorum"
          :rules="[v => !!v || 'Kabul etmelisiniz']"
          required
        ></v-checkbox>
  
        <!-- Gönder Butonu -->
        <v-btn :disabled="!isValid" color="success" @click="submitForm">
          Gönder
        </v-btn>
      </v-form>
    </v-container>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isValid: false,
        form: {
          name: '',
          email: '',
          country: null,
          agree: false,
        },
        countries: ['Türkiye', 'ABD', 'Almanya', 'Fransa'],
      };
    },
    methods: {
      submitForm() {
        if (this.$refs.form.validate()) {
          // Form başarılı bir şekilde doğrulandıysa
          console.log('Form verileri:', this.form);
          // API'ye gönderme işlemi burada yapılabilir
        }
      },
    },
  };
  </script>
  