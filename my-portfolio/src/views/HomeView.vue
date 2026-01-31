<template>
    <WelcomeOverlay />
  <main>
    <HeroSection id="home" />

    <!-- Parallax wrapper -->
    <div class="parallax-wrapper">
      <div class="parallax-bg"></div>

      <AboutSection id="about" />
      <ProjectsSection id="projects" />
      <ContactSection id="contact" />
    </div>
  </main>
</template>

<script setup lang="ts">
import WelcomeOverlay from '../components/WelcomeOverlay.vue'

import HeroSection from '../components/HeroSection.vue'
import AboutSection from '../components/AboutSection.vue'
import ProjectsSection from '../components/ProjectsSection.vue'
import ContactSection from '../components/ContactSection.vue'
</script>

<style scoped>
.parallax-wrapper {
  position: relative;
}

/* ONE background for all 3 sections */
.parallax-bg {
  position: fixed;
  inset: 0;
  background-image: url('../assets/parallax.jpg'); /* public/ */
  background-size: cover;
  background-position: center;
  z-index: -1;
  opacity: 0.35;
  filter: blur(2px) saturate(120%) hue-rotate(200deg);

}
</style>
