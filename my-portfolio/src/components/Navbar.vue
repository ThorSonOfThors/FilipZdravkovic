<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const atTop = ref(true)

const onScroll = () => {
  atTop.value = window.scrollY < 10
}

const scrollTo = (id: string) => {
  const el = document.getElementById(id)
  el?.scrollIntoView({ behavior: 'smooth' })
}

onMounted(() => {
  window.addEventListener('scroll', onScroll, { passive: true })
})

onUnmounted(() => {
  window.removeEventListener('scroll', onScroll)
})
</script>

<template>
  <header :class="['navbar', { transparent: !atTop }]">
    <div class="inner">
      <span class="logo">Filip Zdravković</span>

      <nav>
        <button @click="scrollTo('home')">Home</button>
        <button @click="scrollTo('about')">About</button>
        <button @click="scrollTo('projects')">Projects</button>
        <button @click="scrollTo('contact')">Contact</button>
      </nav>
    </div>
  </header>
</template>

<style scoped>
/* BASE */
.navbar {
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1000;

  background: #000;
  transition: background 0.3s ease, backdrop-filter 0.3s ease;
}

/* TRANSPARENT WHEN SCROLLED */
.navbar.transparent {
  background: rgba(0, 0, 0, 0.6);
  backdrop-filter: blur(8px);
}

.inner {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0.9rem 1.25rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

/* TEXT */
.logo {
  color: white;
  font-weight: 700;
}

nav {
  display: flex;
  gap: 1rem;
}

nav button {
  background: none;
  border: none;
  color: #e5e7eb;
  font-size: 0.95rem;
  cursor: pointer;
}

nav button:hover {
  color: white;
}

/* TABLET+ */
@media (min-width: 768px) {
  nav {
    gap: 1.5rem;
  }
}
</style>
