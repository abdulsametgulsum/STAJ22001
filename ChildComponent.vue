<template>
    <div>
      <h2>Çocuk Bileşen</h2>
      <p>Parent'ten Gelen Mesaj: 
        {{ message }}</p>
      <button @click="sendToParent">
        Parent'a Mesaj Gönder</button>
    </div>
  </template>
  <script>
  export default {
    props: {
      message: String 
    },
    methods: {
      sendToParent() {
        this.$emit('send-event', 'Çocuktan Gelen Mesaj!'); 
      }
    }
  };
  </script>
  