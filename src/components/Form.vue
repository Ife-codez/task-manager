<template>
  <div>
    <label for="name">Name:</label>
    <input type="text" id="name" placeholder="Enter name..." v-model="name">
    <p>Your name is: {{ name }}</p>
    <label for="subscribe">Subscribe</label>
    <input type="checkbox" id="subscribe" v-model="isSubscribed">
    <p>Subscribed: {{ isSubscribed }}</p>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        name: '',
        isSubscribed: false
      }
    }
  }
</script>