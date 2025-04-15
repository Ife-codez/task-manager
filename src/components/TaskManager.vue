<template>
  <div>
    <h2>Task Manager</h2>
    <input type="text" v-model="inputText">
    <button @click="addNewTask">Add Task</button>
    
      <div v-for="(task, index) in tasks" :key="index">
        <h3>{{ task.text }}</h3>
        <h6>{{ task.date }}</h6>
        <button @click="markAsDone(index)">mark as done</button>
        <button @click="deleteTask(index)">delete task</button>
      </div>
   
  </div>

</template>
<script>
  export default {
    data() {
      return {
        inputText: '',
        tasks: []
      }
    },
    methods: {
      addNewTask() {
        if (this.inputText.trim() !== '') {
          const currentDate = new Date().toLocaleString()
          this.tasks.push({
            text: this.inputText,
            date: currentDate,
            done: false
          })
        }
        this.inputText = '';
      },
      deleteTask(index) {
        this.tasks.splice(index, 1)
      },
      markAsDone(index) {
        this.tasks.splice(index, 1)
      }
    }
  }
</script>
<style>
</style>