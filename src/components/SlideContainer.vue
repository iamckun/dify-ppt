<template>
  <div class="slide-container" @keydown="handleKeyDown" tabindex="0" ref="containerRef">
    <Slide v-for="(slide, index) in slides" :key="index" :isActive="currentSlide === index">
      <component :is="slide" />
    </Slide>
    
    <div class="controls">
      <button class="control-btn prev" @click="prevSlide" :disabled="currentSlide === 0">
        <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M15.25 6.75L9.75 12L15.25 17.25" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path>
        </svg>
      </button>
      <div class="slide-indicator">{{ currentSlide + 1 }} / {{ slides.length }}</div>
      <button class="control-btn next" @click="nextSlide" :disabled="currentSlide === slides.length - 1">
        <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M8.75 6.75L14.25 12L8.75 17.25" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path>
        </svg>
      </button>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import Slide from './Slide.vue';
import Slide1 from './slides/Slide1.vue';
import Slide2 from './slides/Slide2.vue';
import Slide3 from './slides/Slide3.vue';
import Slide4 from './slides/Slide4.vue';
import Slide5 from './slides/Slide5.vue';
import Slide6 from './slides/Slide6.vue';

const slides = [Slide1, Slide2, Slide3, Slide4, Slide5, Slide6];
const currentSlide = ref(0);
const containerRef = ref(null);

const nextSlide = () => {
  if (currentSlide.value < slides.length - 1) {
    currentSlide.value++;
  }
};

const prevSlide = () => {
  if (currentSlide.value > 0) {
    currentSlide.value--;
  }
};

const handleKeyDown = (event) => {
  if (event.key === 'ArrowRight' || event.key === ' ') {
    nextSlide();
  } else if (event.key === 'ArrowLeft') {
    prevSlide();
  }
};

onMounted(() => {
  if (containerRef.value) {
    containerRef.value.focus();
  }
});
</script>

<style scoped>
.slide-container {
  position: relative;
  width: 100%;
  height: 100vh;
  overflow: hidden;
  outline: none;
}

.controls {
  position: fixed;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  align-items: center;
  gap: 1rem;
  z-index: 100;
  background: rgba(10, 25, 47, 0.8);
  padding: 0.5rem 1rem;
  border-radius: 8px;
  backdrop-filter: blur(5px);
  border: 1px solid rgba(100, 255, 218, 0.2);
}

.control-btn {
  background: none;
  border: none;
  color: #64ffda;
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  border-radius: 50%;
  transition: all 0.3s ease;
}

.control-btn:hover:not(:disabled) {
  background: rgba(100, 255, 218, 0.1);
}

.control-btn:disabled {
  color: #546178;
  cursor: not-allowed;
}

.control-btn svg {
  width: 24px;
  height: 24px;
}

.slide-indicator {
  font-size: 0.9rem;
  color: #a8b2d1;
  font-family: monospace;
  padding: 0 1rem;
}
</style> 