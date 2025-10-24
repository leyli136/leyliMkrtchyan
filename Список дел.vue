<template>
  <div class="app">
    <h1>Список дел</h1>
    <p>Задач: {{ tasks.length }}</p>
    <div class="tasks">
      <TaskItem
        v-for="t in tasks"
        :key="t.id"
        :task="t"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import TaskItem from './components/TaskItem.vue'

const tasks = ref([
  { id: '1', title: 'Купить кофе', text: 'Эспрессо' },
  { id: '2', title: 'Прогулка', text: 'Парк в 18:00' },
  { id: '3', title: 'Ответить на письма', text: 'Важные клиенты' },
  { id: '4', title: 'Полить цветы', text: 'На балконе и в гостиной' }
])
</script>

<style scoped>
.app {
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 100vh;
  padding: 24px;
  background: #f8f9fa;
  color: #333;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
}

h1 {
  margin-bottom: 4px;
  font-weight: 600;
  color: #2c3e50;
}

p {
  margin-top: 0;
  margin-bottom: 20px;
  color: #7f8c8d;
  font-size: 0.95rem;
}

.tasks {
  display: flex;
  flex-direction: column;
  gap: 16px;
  width: 100%;
  max-width: 520px;
}
</style>