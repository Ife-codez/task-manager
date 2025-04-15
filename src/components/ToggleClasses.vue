<template>
  <div>
    <h2
    :class="{ active: isActive, warning: hasWarning }"
    >Watch my style change</h2>
    <button @click="isActive = !isActive">Toggle active</button>
    <button
      @click="hasWarning = !hasWarning"
    >Toggle warning</button>
  </div>

</template>
<script>
  export default {
    data() {
      return {
        isActive: false,
        hasWarning: false
      }
    }
  } 
</script>
<style>
  .active {
    color: green;
    font-weight: medium;
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  }
  .warning {
    color: red;
    font-weight: bold;
    text-decoration: underline;
  }
</style>