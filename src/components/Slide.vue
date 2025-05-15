<template>
  <div class="slide" :class="{ active: isActive }">
    <slot></slot>
  </div>
</template>

<script setup>
defineProps({
  isActive: {
    type: Boolean,
    default: false
  }
});
</script>

<style scoped>
.slide {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background: linear-gradient(135deg, #0a192f, #0f2942);
  color: #e6f1ff;
  padding: 2rem;
  position: absolute;
  top: 0;
  left: 0;
  opacity: 0;
  visibility: hidden;
  transition: opacity 0.5s ease, visibility 0.5s;
  overflow: hidden;
  z-index: 0;
}

.slide.active {
  opacity: 1;
  visibility: visible;
  z-index: 10;
}

.slide::before {
  content: '';
  position: absolute;
  width: 200%;
  height: 200%;
  background: linear-gradient(45deg, transparent 49%, rgba(0, 149, 255, 0.1) 50%, transparent 51%);
  top: -50%;
  left: -50%;
  animation: techGrid 20s linear infinite;
  z-index: -1;
}

@keyframes techGrid {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style> 