<template>
    <div id="app">
      <h1>{{ message }}</h1>
      <img :src="imageUrl" alt="Vue.js logo" width="200">
      <div>
        <label for="name">Adınızı Girin:</label>
        <input type="text" v-model="name">
        <p>Merhaba, {{ name }}!</p>
      </div>
      <div v-if="isVisible">
        <p>Bu mesaj sadece görünür olduğunda gösterilir.</p>
      </div>
      <button @click="toggleVisibility">Görünürlüğü Değiştir</button>
      <ul>
        <li v-for="item in items" :key="item">{{ item }}</li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        message: "Vue.js ile Veri Gösterimi",
        imageUrl: "https://vuejs.org/images/logo.png",
        name: "",
        isVisible: true,
        items: ["Elma", "Armut", "Portakal"]
      };
    },
    methods: {
      toggleVisibility() {
        this.isVisible = !this.isVisible;
      }
    }
  };
  </script>
  