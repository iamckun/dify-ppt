<template>
  <div class="slide-content">
    <div class="title-container">
      <h1 class="main-title">Dify 技术分享</h1>
      <div class="subtitle">打造智能应用的一站式开发平台</div>
    </div>
    <div class="decoration">
      <div class="tech-circle"></div>
      <div class="tech-lines"></div>
    </div>
  </div>
</template>

<script setup>
// Slide 1 - 封面页
</script>

<style scoped>
.slide-content {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  overflow: hidden;
}

.title-container {
  z-index: 2;
  text-align: center;
  animation: fadeIn 1.5s ease-out;
  position: relative;
}

.main-title {
  font-size: 4.5rem;
  font-weight: 700;
  margin-bottom: 1rem;
  background: linear-gradient(90deg, #4facfe 0%, #00f2fe 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  letter-spacing: 2px;
  text-shadow: 0 0 15px rgba(79, 172, 254, 0.5);
}

.subtitle {
  font-size: 1.8rem;
  color: #a8b2d1;
  margin-top: 1rem;
  letter-spacing: 1px;
}

.decoration {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.tech-circle {
  position: absolute;
  width: 40vw;
  height: 40vw;
  border-radius: 50%;
  border: 2px solid rgba(0, 149, 255, 0.1);
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  animation: rotate 20s linear infinite;
}

.tech-circle::before, .tech-circle::after {
  content: '';
  position: absolute;
  width: 70%;
  height: 70%;
  border-radius: 50%;
  border: 2px solid rgba(0, 212, 255, 0.1);
  top: 15%;
  left: 15%;
  animation: rotate 15s linear infinite reverse;
}

.tech-circle::after {
  width: 40%;
  height: 40%;
  top: 30%;
  left: 30%;
  border: 2px solid rgba(0, 149, 255, 0.2);
  animation-duration: 10s;
}

.tech-lines {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  overflow: hidden;
}

.tech-lines::before, .tech-lines::after {
  content: '';
  position: absolute;
  height: 2px;
  width: 70vw;
  background: linear-gradient(90deg, transparent, rgba(0, 149, 255, 0.2), transparent);
  top: 30%;
  left: 50%;
  transform: translateX(-50%) rotate(25deg);
}

.tech-lines::after {
  top: 70%;
  transform: translateX(-50%) rotate(-25deg);
}

@keyframes rotate {
  0% {
    transform: translate(-50%, -50%) rotate(0deg);
  }
  100% {
    transform: translate(-50%, -50%) rotate(360deg);
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style> 