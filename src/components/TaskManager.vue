<template>
  <div class="body">

    <div class="t_m">
      <h2>Task Manager</h2>
      <input type="text" v-model="inputText">
      <button @click="addNewTask">Add Task</button>
      
        <!-- <div v-for="(task, index) in tasks" :key="index">
          <h3>{{ task.text }}</h3>
          <h6>{{ task.date }}</h6>
          <button @click="markAsDone(index)"><input type="checkbox"></button>
          <button @click="deleteTask(index)">
            <svg :width="size" :height="size" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M135.2 17.7L128 32 32 32C14.3 32 0 46.3 0 64S14.3 96 32 96l384 0c17.7 0 32-14.3 32-32s-14.3-32-32-32l-96 0-7.2-14.3C307.4 6.8 296.3 0 284.2 0L163.8 0c-12.1 0-23.2 6.8-28.6 17.7zM416 128L32 128 53.2 467c1.6 25.3 22.6 45 47.9 45l245.8 0c25.3 0 46.3-19.7 47.9-45L416 128z"/></svg>
          </button>
        </div> -->

        <TaskList @mark="markAsDone" @delete="deleteTask" :tasks="tasks" :done="true" />
        <TaskList @mark="markAsDone" @delete="deleteDoneTask" :tasks="doneTasks" :done="false" />
     
    </div>
  </div>

</template>
<script>
import TaskList from './TaskList.vue';

  export default {
    components: {
      TaskList
  },
    data() {
      return {
        inputText: '',
        tasks: [],
        size: 15,
        doneTasks: []
      }
    },
    methods: {
      addNewTask() {
        if (this.inputText.trim() !== '') {
          const currentDate = new Date().toLocaleString()
          this.tasks.push({
            id: Date.now(),
            text: this.inputText,
            date: currentDate,
            done: false
          })
        }
        this.inputText = '';
      },
      // deleteTask(index) {
      //    return this.tasks.splice(index, 1)
      // },
      deleteTask(id) {
        this.tasks = this.tasks.filter(text => text.id !== id)
      },
      deleteDoneTask(id) {
        this.doneTasks = this.doneTasks.filter(text => text.id !== id)
      },
      markAsDone(index, id) {
        this.doneTasks.push(this.tasks[index])
        this.deleteTask(id)
      }
    }
  }
</script>
<style scoped>
.t_m{
  border :1px solid red;
  padding: 20px;
  text-align: center;
}
.body {
    width: 100%;
    min-height: 100%;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content:  center;
  }
</style>