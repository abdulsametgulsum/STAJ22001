<template>
    <div>
      <h1>Kullanıcılar Listesi</h1>
      <ul>
        <li v-for="user in users" :key="user.id">
          {{ user.name }} - {{ user.email }}
        </li>
      </ul>
    </div>
  </template>
  <script>
  import axios from 'axios';
  export default {
    data() {
      return {
        users: [], 
      };
    },
    created() {
      axios.get('http://localhost:5225/api/Kullanici')
        .then(response => {
          this.users = response.data; 
        })
        .catch(error => {
          console.error('Veri çekme hatası:', error);
        });
    }
  };
  </script>
  