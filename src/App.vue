<template>
  <div id="app">
    <form>
      <input v-model="taskUser" />
    </form>
    {{taskUser}}
    <ul>
      <li v-for="task in tasks" :key="task.id">
        <Task :title="task.title" />
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
  } 
}
</script>

<style>
</style>
