<template>
  <div class="container">
   <Header title="Header Text" />
   <Tasks @delete-task="deleteTask" :tasks="tasks" />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Tasks from './components/tasks/Tasks.vue'

export default {
  name: 'App',
  components: {
    Header,
    Tasks
  },
  data () {
    return {
      tasks: []
    }
  },
  methods: {
    deleteTask (id) {
      this.tasks = this.tasks.filter((task) => task.id !== id)
    }
  },
  created () {
    this.tasks = [
      {
        id: 1,
        text: 'Doctors Appointment',
        day: 'May 1st at 2:38pm',
        reminder: true
      },
      {
        id: 2,
        text: 'School Appointment',
        day: 'May 4th at 2:38pm',
        reminder: true
      },
      {
        id: 3,
        text: 'School meeting',
        day: 'Jun 1st at 2:38pm',
        reminder: false
      }
    ]
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  height: 100%;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
}
.btn:focus{
  outline: none;
}

</style>
