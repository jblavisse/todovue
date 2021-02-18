<template>
  <div id="app">
    <form>
      <input v-model="taskUser" />
      <button @click="addTask">OK</button>
    </form>
    {{taskUser}}
    <ul>
      <li v-for="task in tasks" :key="task.id">
        <Task :id="task.id" :title="task.title" />
      </li>
    </ul>
  </div>
</template>

<script>
import Task from './components/Task';

export default {
  name: 'App',
  components: {
    Task
  },
  data: function() {
    return {
    tasks:  [
      {id: 1, title: "Faire à manger", completed: false},
      {id: 2, title: "Faire la vaiselle", completed: true},
      {id: 3, title: "Dormir", completed:false}
    ],
    taskUser: ""
    }
  },
  methods: {
    addTask: function(e) {
      e.preventDefault();
      console.log(this.taskUser);

      this.tasks.push({
        id: this.tasks.length+1,
        title: this.taskUser,
        completed:false
      });

      this.taskUser = "";
    }
  }
}
</script>

<style>
</style>
