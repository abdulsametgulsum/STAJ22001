<template>
    <div id="app">
      <button @click="sayHello">Merhaba De</button>
      <p>{{ message }}</p>
      <form @submit.prevent="handleSubmit">
        <label for="username">Kullanıcı Adı:</label>
        <input type="text" v-model="username" id="username" required>
        <label for="email">E-posta:</label>
        <input type="email" v-model="email" id="email" required>
        <button type="submit">Gönder</button>
      </form>
      <p v-if="submitted">Kullanıcı Adı: {{ username }}, E-posta: {{ email }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        message: "",
        username: "",
        email: "",
        submitted: false,
      };
    },
    methods: {
      sayHello() {
        this.message = "Merhaba, Vue.js!";
      },
      handleSubmit() {
        this.submitted = true;
      }
    }
  };
  </script>
  