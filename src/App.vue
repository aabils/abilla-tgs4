<template>
  <div id="app">
    <h1>Parent Component</h1>
    <task-list :tasks="tasks" @task-clicked="handleTaskClicked"></task-list>
    <task-detail :task="selectedTask"></task-detail>
  </div>
</template>

<script>
import TaskList from './components/TaskList.vue';
import TaskDetail from './components/TaskDetail.vue';

export default {
  components: {
    TaskList,
    TaskDetail
  },
  data() {
    return {
      tasks: [
        { name: 'Belajar', completed: false },
        { name: 'Makan siang', completed: true },
        { name: 'Bermain', completed: false }
      ],
      selectedTask: null
    };
  },
  methods: {
    handleTaskClicked(task) {
      this.selectedTask = task;
    }
  }
}
</script>

<style scoped>
#app {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  background-color: #1a446d;
  border: 1px solid #000000;
  border-radius: 5px;
}

h1 {
  color: #0b1c2d;
  text-align: center;

  margin-bottom: 20px;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
}
</style>
