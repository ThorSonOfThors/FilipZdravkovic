<script setup lang="ts">
import { onMounted, ref } from 'vue'

const visible = ref(true)

onMounted(() => {
  setTimeout(() => {
    visible.value = false
  }, 800)
})
</script>

<template>
  <div v-if="visible" class="overlay">
    <h1>Welcome</h1>
  </div>
</template>

<style scoped>
.overlay {
  position: fixed;
  inset: 0;
  background: #111827;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9999;
  animation: fadeOut 0.8s ease forwards;
  animation-delay: 0.5s;
}

h1 {
  font-size: 2rem;
  letter-spacing: 0.05em;
}

@keyframes fadeOut {
  to {
    opacity: 0;
    transform: translateY(-10px);
  }
}
</style>
