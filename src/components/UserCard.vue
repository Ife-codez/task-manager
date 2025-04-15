<template>
  <h2>Hello, {{ user.name }}</h2>
  <p>Age: {{ user.age }}</p>
  <p>Location : {{ user.location }}</p>
</template>
<script>
  export default {
    props: {
      user: Object
    }
  }
</script>