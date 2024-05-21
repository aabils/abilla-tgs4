<template>
  <ul class="task-list">
    <task-item 
      v-for="(task, index) in tasks" 
      :key="index" 
      :task="task" 
      @task-clicked="handleTaskClicked"
    ></task-item>
  </ul>
</template>

<script>
import TaskItem from './TaskItem.vue';

export default {
  components: {
    TaskItem
  },
  props: {
    tasks: Array
  },
  methods: {
    handleTaskClicked(task) {
      this.$emit('task-clicked', task);
    }
  }
}
</script>

<style scoped>
.task-list {
  list-style-type: none;
  padding: 0;
}

.task-list li {
  padding: 10px;
  border-bottom: 1px solid #ddd;
  cursor: pointer;
}

.task-list li:hover {
  background-color: #f0f0f0;
}
</style>
