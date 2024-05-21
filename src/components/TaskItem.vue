<template>
  <li @click="handleClick" :class="{ 'completed': task.completed }">{{ task.name }}</li>
</template>

<script>
export default {
  props: {
    task: Object
  },
  methods: {
    handleClick() {
      this.$emit('task-clicked', this.task);
    }
  }
}
</script>

<style scoped>
.completed {
  text-decoration: line-through;
  color: #888;
}
</style>
