<template>
  <div id="app">
    <form>
      <input v-model="taskUser" />
      <button @click="addTask">OK</button>
    </form>
    {{taskUser}}
    <ul>
      <li v-for="task in tasks" :key="task.id">
        <Task :id="task.id" :title="task.title" :completed="task.completed" />
      </li>
    </ul>
  </div>
</template>

<script>
import Task from './components/Task';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Task
  },
  data: function() {
    return {
    tasks:  [],
    taskUser: ""
    }
  },
  mounted () {
    axios.get("https://jsonplaceholder.typicode.com/todos")
    .then(res => {
      this.tasks = res.data;
    })
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
