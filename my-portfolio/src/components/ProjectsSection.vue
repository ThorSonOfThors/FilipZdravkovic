<script setup lang="ts">
const projects = [
  {
    name: 'E-Commerce online application ',
    url: 'https://github.com/ThorSonOfThors/Batik-Shop.git'
  },
  {
    name: 'Sales website with automated emails',
    url: 'https://github.com/ThorSonOfThors/TintorSajt.git'
  },
  {
    name: 'Portfolio Website for my father',
    url: 'https://milojezdravkovicwebsite.vercel.app/'
  },
    {
    name: 'Genetic Algorithms',
    url: 'https://github.com/ThorSonOfThors/MST_Evolutionary-Algorithm.git'
  },
  {
    name: 'Neural Networks',
    url: 'https://github.com/ThorSonOfThors/Convolutional-Neural-Networks-PyTorch-vs-TensorFlow-.git'
  },
   {
    name: 'Working on invention of a new optimizer in NN training',
    url: 'https://github.com/ThorSonOfThors/Convolutional-Neural-Networks-PyTorch-vs-TensorFlow-.git'
  },
  {
    name: 'Tampermonkey Script for a Mini Youtube browser extension',
    url: 'https://github.com/ThorSonOfThors/Mini-Youtube-Tampermonkey-Script.git'
  }
]
</script>

<template>
  <section class="page">
    <h2>Projects</h2>

    <ul class="projects">
      <li v-for="project in projects" :key="project.name">
        <a
          :href="project.url"
          target="_blank"
          rel="noopener"
        >
          {{ project.name }}
        </a>
      </li>
    </ul>
    <p>more projects coming up...</p>
  </section>
</template>

<style scoped>
.projects {
  list-style: none;
  padding: 0;
  margin: 1.5rem 0 0;
  display: grid;
  gap: 0.75rem;
}

.projects a {
  display: block;
  padding: 0.75rem 1rem;

  border-radius: 6px;
  text-decoration: none;

  color: var(--text);
  background: rgba(0, 0, 0, 0.03);

  transition: background 0.15s ease;
}

.projects a:hover {
  background: rgba(0, 0, 0, 0.07);
}
</style>
