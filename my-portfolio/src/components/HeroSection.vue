<script setup lang="ts">
import { ref } from 'vue'

const flipped = ref(false)

const downloadCV = () => {
  const link = document.createElement('a')
  link.href = '/Filip_Zdravkovic_CV.pdf'
  link.download = 'Filip_Zdravkovic_CV.pdf'
  link.click()
}

const flipImage = () => {
  flipped.value = !flipped.value
}
</script>

<template>
  <section class="hero" id="home">
    <div class="content">
      <div class="text">
        <h2>Hello, I’m Filip Zdravković</h2>
        <h3>Software Engineer & Web Developer</h3>

        <p>
          I design and build performant, user-focused applications —
          from modern web interfaces to robust backend systems —
          with a strong foundation in computer science.
        </p>


        <button @click="downloadCV">Download CV</button>
      </div>

      <div class="image">
        <div
          class="coin"
          :class="{ flipped }"
          @click="flipImage"
          role="button"
          aria-label="Flip profile picture"
        >
          <div class="coin-face front">
            <img src="../assets/profile.jpg" alt="Filip Zdravković" />
          </div>
          <div class="coin-face back">
            <img src="../assets/pfp.jpg" alt="Filip Zdravković alternate" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  background: linear-gradient(
      rgba(255, 255, 255, 0.92),
      rgba(167, 176, 199, 0.92)
    ),
    url('../assets/hero-bg.jpg') center / cover no-repeat;
}

/* LAYOUT */
.content {
  max-width: 1100px;
  margin: 0 auto;
  padding: 3rem 1.25rem;
  display: grid;
  grid-template-columns: 1fr;
  gap: 3rem;
}

/* TEXT */
.text h2 {
  font-size: 2.25rem;
  margin: 0;
}

.text h3 {
  font-size: 1.25rem;
  color: #6b7280;
  margin: 0.5rem 0 1.5rem;
}

.text p {
  max-width: 500px;
  font-size: 1.1rem;
}

/* BUTTON */
button {
  margin-top: 2rem;
  padding: 0.75rem 1.75rem;
  border-radius: 6px;
  border: none;
  cursor: pointer;
  background: #111827;
  color: white;
  font-size: 1rem;

  transition:
    transform 0.15s ease,
    box-shadow 0.15s ease,
    background-color 0.15s ease;
}

button:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(17, 24, 39, 0.25);
}

button:active {
  transform: translateY(0);
  box-shadow: 0 4px 10px rgba(17, 24, 39, 0.2);
}

button:focus-visible {
  outline: none;
  box-shadow: 0 0 0 3px rgba(17, 24, 39, 0.4);
}

/* IMAGE */
.image {
  display: flex;
  justify-content: center;
}

/* COIN FLIP */
.coin {
  width: 220px;
  height: 220px;
  position: relative;
  transform-style: preserve-3d;
  transition: transform 0.8s cubic-bezier(0.4, 0.2, 0.2, 1);
  cursor: pointer;
  perspective: 1000px;
}

.coin.flipped {
  transform: rotateY(180deg);
}

.coin-face {
  position: absolute;
  inset: 0;
  backface-visibility: hidden;
  border-radius: 50%;
  overflow: hidden;
}

.coin-face img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 50%;
  border: 4px solid white;
}

/* BACK */
.coin-face.back {
  transform: rotateY(180deg);
}

/* TABLET */
@media (min-width: 768px) {
  .content {
    grid-template-columns: 1.2fr 0.8fr;
    align-items: center;
  }

  .text h2 {
    font-size: 3rem;
  }

  .coin {
    width: 260px;
    height: 260px;
  }
}

/* DESKTOP */
@media (min-width: 1024px) {
  .coin {
    width: 300px;
    height: 300px;
  }
}
</style>
