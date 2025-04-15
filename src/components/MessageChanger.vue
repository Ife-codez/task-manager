<template>
  <div>
    <h2 v-if="isVisible">{{ message }}</h2>
    <h2 v-else>{{ messsage }}</h2>
    <button 
    @click = "toggleVisibility"
    >Toggle</button>
  </div>
</template>

<script>
 export default {
  data() {
    return {
      message: 'This message will show conditionally',
      messsage: 'This message shows because the other one is hidden',
      isVisible: true
    }
  },
  methods: {
    toggleVisibility() {
      this.isVisible = !this.isVisible;
    }
  }
 }

</script>