<template>
  <!-- <div>
    <messageChanger />
  </div>
  <div>
    <UserCard :user="userInfo"/>
  </div>
  <div>
    <UsersList :userss="userList"/>
  </div>
  <Form />
  <div>
    <CustomInput v-model="userInput"/>
    <p>You typed: {{ userInput }}</p>
  </div>
  <div>
    <ToggleClasses />
  </div> -->
  <div class="obody">
    <TaskManager />
  </div>
</template>

<script>
import messageChanger from './components/MessageChanger.vue'
import UserCard from './components/UserCard.vue'
import UsersList from './components/UsersList.vue'
import Form from './components/Form.vue'
import CustomInput from './components/CustomInput.vue'
import ToggleClasses from './components/ToggleClasses.vue'
import TaskManager from './components/TaskManager.vue'
export default {
  components: {
    // messageChanger,
    // UserCard,
    // UsersList,
    // Form,
    // CustomInput,
    // ToggleClasses,
    TaskManager,
  },
  data() {
    return {
      userInfo: {
        name: 'Zainab',
        age: 30,
        location: 'Lagos',
      },
      userList: [
        {name: 'Opeyemi', age: 20},
        {name: 'Ayomide', age: 25},
        {name: 'Ifedola', age: 30}
      ],
      userInput: '',
      message: 'Hello!'
    }
  },
  mounted() {
    console.log('component has been mounted!')
    console.log(this.message)
  }
}
</script>
<style>
  
</style>