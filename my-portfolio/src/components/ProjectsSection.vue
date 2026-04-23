<script setup lang="ts">
const projects = [
  
  {
    name: 'Zero-cost comunity website with auth, admin-managment and user friendly UI',
    url: 'https://davincy.vercel.app/'
  },
  {
    name: 'E-Commerce online application ',
    url: 'https://github.com/ThorSonOfThors/Batik-Shop.git'
  },

  {
    name: 'Online Application designed for pixel-art with SEO operations and advanced 2D grid tools ',
    url: 'https://artofpixels.vercel.app/'
  },

   {
    name: 'SEO specialized website with reactive user-input results ',
    url: 'https://tools4renovation.vercel.app/'
  },

  {
    name: 'Online application with GSAP scrolling effects and backend event manager',
    url: 'https://akatsuki-gamma.vercel.app/home'
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
  },
  {
    name: 'SEO online application using NUXT',
    url: 'https://tools4renovation.vercel.app/'
  }
  
]

const isGithub = (url: string) => url.includes('github.com')
</script>

<template>
  <section class="page">
    <h2>Projects</h2>

    <div class="projects">
      <div
        v-for="project in projects"
        :key="project.name"
        class="project-card"
      >

        <!-- ✅ GITHUB → IMAGE PREVIEW -->
        <div v-if="isGithub(project.url)">
          <div class="preview-wrapper">
            <img src="/git.jpeg" alt="GitHub project" />

            <a
              :href="project.url"
              target="_blank"
              rel="noopener"
              class="overlay"
            ></a>
          </div>

          <p class="title">{{ project.name }}</p>
        </div>

        <!-- ✅ WEBSITE → IFRAME PREVIEW -->
        <div v-else>
          <div class="preview-wrapper">
            <iframe :src="project.url" loading="lazy"></iframe>

            <a
              :href="project.url"
              target="_blank"
              rel="noopener"
              class="overlay"
            ></a>
          </div>

          <p class="title">{{ project.name }}</p>
        </div>

      </div>
    </div>

    <p>more projects coming up...</p>
  </section>
</template>

<style scoped>
.projects {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 1.5rem;
  margin-top: 1.5rem;
}

.project-card {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

/* Preview */
.preview-wrapper {
  position: relative;
  width: 100%;
  height: 200px;
  overflow: hidden;
  border-radius: 10px;
  background: #000;
}

.preview-wrapper iframe {
  width: 1200px;
  height: 800px;
  border: none;
  transform: scale(0.25);
  transform-origin: top left;
  pointer-events: none;
}

.overlay {
  position: absolute;
  inset: 0;
  z-index: 2;
}

.title {
  font-size: 0.9rem;
}

/* GitHub fallback style */
.github-item {
  display: block;
  padding: 1rem;
  border-radius: 8px;
  text-decoration: none;
  background: rgba(0,0,0,0.05);
  transition: background 0.2s;
}

.github-item:hover {
  background: rgba(0,0,0,0.1);
}
</style>
