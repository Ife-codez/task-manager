<template>
  <div>
    <ul>
      <li v-for="(user, index) in userss" :key="index">
        {{ index + 1 }}. {{ user.name }} - Age: {{ user.age }}
      </li>
    </ul>
  </div>
</template>
<script>
  export default {
    props : {
      userss: Array
    }
  }
</script>