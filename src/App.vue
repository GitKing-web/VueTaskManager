<template>
<div class="container">
  <Header_com @toggle-add-task="ToggleAddTask" title="Task Manager" :toggleText="showAddTask" />
  <div v-show="showAddTask">
    <AddTask_com @add-task="addTask" />
  </div>
  <Tasks_com @delete-task="deleteTask" :tasks="tasks" />
</div>
</template>

<script>

import Header_com from './components/Header'
import Tasks_com from './components/Tasks'
import AddTask_com from './components/AddTask'

export default {
  name: 'App',
  components: {
    Header_com,
    Tasks_com,
    AddTask_com
  },
  data() {
    return {
      tasks: [],
      showAddTask: false
    }
  },
  methods: {
    ToggleAddTask() {
      this.showAddTask = !this.showAddTask
    },
    addTask(task){
      this.tasks = [...this.tasks, task]
    },
    deleteTask(id){
      if(confirm('Are you sure you want to delete task?')){

        this.tasks = this.tasks.filter((task) => task.id !== id )
      }
    }
  },
  created(){
    this.tasks = [
      {
        id: 1,
        text: 'meeting with boss',
        day: '5th march 2023',
        reminder: true
      },

      {
        id: 2,
        text: 'meeting with boss',
        day: '5th march 2023',
        reminder: false
      },

      {
        id: 3,
        text: 'take out the trash',
        day: '5th march 2023',
        reminder: true
      }
    ]
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
html,
body{
  height: 100vh;
}
.container{
  width: 60%;
  position: relative;
  padding: 2% 6%;
  margin-top: 20vh;
  margin-left: 12em;
  margin-right: 20em;
  border-radius: 6px;
  /* height: auto; */
  border: .78px solid #6b6a6a;
}
.header{
  display: flex;
  justify-content: space-between;
}
.btn{
  padding: 10px;
  background-color: #141212;
  color: #fff;
  border: none;
  border-radius: 2px;
}
.add-task{
  margin-top: 3rem;
}
legend{
  margin-top: 8px;

}
input{
  width: 100%;
  padding: .45rem;
  margin-top: 1em;
}

.tasks{
  margin-top: 3rem;
}

</style>
