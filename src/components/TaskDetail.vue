<template>
  <div class="task-detail" v-if="task">
    <h2>Detail data dari parent</h2>
    <p>Nama: {{ task.name }}</p>
    <p>Status: {{ task.completed ? 'Selesai' : 'Belum Selesai' }}</p>
  </div>
  <div class="task-detail" v-else>
    <p>Pilih satu untuk melihat detailnya.</p>
  </div>
</template>

<script>
export default {
  props: {
    task: Object
  }
}
</script>

<style scoped>
.task-detail {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
  margin-top: 10px;
}
</style>
