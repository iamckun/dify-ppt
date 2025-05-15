<template>
  <div class="slide-content">
    <div class="tech-bg">
      <div class="circuit-line line-1"></div>
      <div class="circuit-line line-2"></div>
      <div class="circuit-line line-3"></div>
      <div class="circuit-dot dot-1"></div>
      <div class="circuit-dot dot-2"></div>
      <div class="circuit-dot dot-3"></div>
      <div class="tech-hexagon hex-1"></div>
      <div class="tech-hexagon hex-2"></div>
      <div class="tech-hexagon hex-3"></div>
      <div class="data-grid"></div>
    </div>
    
    <h2 class="section-title">Dify的出现解决了什么问题？</h2>
    
    <div class="content-container">
      <div class="problem-section">
        <h3 class="subsection-title">LLM应用开发的挑战</h3>
        
        <div class="tech-challenge-grid">
          <div class="challenge-card" v-for="(challenge, index) in challenges" :key="index" :style="{ animationDelay: `${0.2 * (index + 1)}s` }">
            <div class="card-icon">
              <div class="pulse-circle"></div>
            </div>
            <div class="card-text">{{ challenge }}</div>
            <div class="card-glint"></div>
          </div>
        </div>
      </div>

      <div class="visualization-container">
        <div class="tech-diagram">
          <svg viewBox="0 0 200 200" class="llm-diagram">
            <circle cx="100" cy="100" r="50" class="diagram-circle outer-circle" />
            <circle cx="100" cy="100" r="35" class="diagram-circle middle-circle" />
            <circle cx="100" cy="100" r="20" class="diagram-circle inner-circle" />
            <path d="M100,20 L100,40" class="diagram-line" />
            <path d="M100,160 L100,180" class="diagram-line" />
            <path d="M20,100 L40,100" class="diagram-line" />
            <path d="M160,100 L180,100" class="diagram-line" />
            <path d="M30,30 L45,45" class="diagram-line" />
            <path d="M155,155 L170,170" class="diagram-line" />
            <path d="M30,170 L45,155" class="diagram-line" />
            <path d="M155,45 L170,30" class="diagram-line" />
            <text x="100" y="105" class="diagram-text">LLM</text>
          </svg>
        </div>
        
        <div class="stats-container">
          <div class="stat-item">
            <div class="stat-value">75%</div>
            <div class="stat-label">开发效率提升</div>
            <div class="stat-bar"><div class="stat-fill" style="width: 75%"></div></div>
          </div>
          <div class="stat-item">
            <div class="stat-value">63%</div>
            <div class="stat-label">成本节约</div>
            <div class="stat-bar"><div class="stat-fill" style="width: 63%"></div></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// Slide 2 - Dify解决的问题
import { ref } from 'vue';

const challenges = [
  '开发LLM应用的技术门槛高',
  '从原型到生产的转化困难',
  '缺乏完整的开发和运维工具链',
  '模型管理与多模型集成复杂'
];
</script>

<style scoped>
.slide-content {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  padding: 2rem 4rem;
  overflow: hidden;
  position: relative;
  color: #ccd6f6;
}

/* 背景科技元素 */
.tech-bg {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  overflow: hidden;
  z-index: -1;
}

.circuit-line {
  position: absolute;
  background: linear-gradient(90deg, rgba(100, 255, 218, 0.1), rgba(100, 255, 218, 0.4));
  height: 1px;
}

.line-1 {
  width: 40%;
  top: 20%;
  left: -5%;
  transform: rotate(15deg);
}

.line-2 {
  width: 30%;
  bottom: 30%;
  right: 10%;
  transform: rotate(-25deg);
}

.line-3 {
  width: 20%;
  top: 60%;
  left: 5%;
  transform: rotate(45deg);
}

.circuit-dot {
  position: absolute;
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background-color: rgba(100, 255, 218, 0.7);
  box-shadow: 0 0 10px rgba(100, 255, 218, 0.7);
  animation: pulse 3s infinite;
}

.dot-1 {
  top: 20%;
  right: 20%;
  animation-delay: 0.5s;
}

.dot-2 {
  bottom: 25%;
  left: 15%;
  animation-delay: 1s;
}

.dot-3 {
  top: 50%;
  right: 30%;
  animation-delay: 1.5s;
}

.tech-hexagon {
  position: absolute;
  width: 100px;
  height: 115px;
  background-color: rgba(79, 172, 254, 0.05);
  clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);
  opacity: 0.5;
}

.hex-1 {
  top: 10%;
  left: 30%;
  transform: rotate(30deg) scale(1.5);
  border: 1px solid rgba(100, 255, 218, 0.1);
}

.hex-2 {
  bottom: 5%;
  right: 20%;
  transform: rotate(15deg) scale(1.2);
  border: 1px solid rgba(79, 172, 254, 0.1);
}

.hex-3 {
  top: 40%;
  left: 10%;
  transform: rotate(-15deg) scale(0.8);
  border: 1px solid rgba(100, 255, 218, 0.1);
}

.data-grid {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: 
    radial-gradient(rgba(100, 255, 218, 0.05) 1px, transparent 1px),
    radial-gradient(rgba(100, 255, 218, 0.05) 1px, transparent 1px);
  background-size: 30px 30px;
  background-position: 0 0, 15px 15px;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 600;
  margin-bottom: 2rem;
  color: #64ffda;
  animation: slideInDown 1s ease-out;
  position: relative;
  align-self: flex-start;
  text-shadow: 0 0 10px rgba(100, 255, 218, 0.3);
  margin-top: 1rem;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 0;
  width: 150px;
  height: 3px;
  background: linear-gradient(90deg, #64ffda, transparent);
}

.content-container {
  display: flex;
  justify-content: space-between;
  gap: 2rem;
  flex: 1;
  margin-top: 1rem;
}

.problem-section {
  width: 55%;
  animation: fadeInLeft 1s ease-out;
}

.subsection-title {
  font-size: 1.8rem;
  color: #4facfe;
  margin-bottom: 1.5rem;
  font-weight: 500;
  text-shadow: 0 0 8px rgba(79, 172, 254, 0.3);
}

/* 挑战卡片网格 */
.tech-challenge-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-gap: 1.5rem;
}

.challenge-card {
  background: rgba(22, 28, 41, 0.7);
  border: 1px solid rgba(100, 255, 218, 0.2);
  border-radius: 8px;
  padding: 1.2rem;
  display: flex;
  align-items: center;
  position: relative;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
  animation: fadeIn 0.5s ease-out;
  animation-fill-mode: both;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  overflow: hidden;
}

.challenge-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
  border-color: rgba(100, 255, 218, 0.5);
}

.card-icon {
  min-width: 40px;
  height: 40px;
  margin-right: 1rem;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  background: rgba(100, 255, 218, 0.1);
  border-radius: 50%;
}

.pulse-circle {
  width: 12px;
  height: 12px;
  background-color: #64ffda;
  border-radius: 50%;
  position: relative;
  box-shadow: 0 0 10px rgba(100, 255, 218, 0.7);
}

.pulse-circle::before {
  content: '';
  position: absolute;
  width: 24px;
  height: 24px;
  border-radius: 50%;
  border: 2px solid #64ffda;
  top: -8px;
  left: -8px;
  opacity: 0;
  animation: pulse 2s infinite;
}

.card-text {
  font-size: 1.1rem;
  color: #ccd6f6;
  line-height: 1.4;
}

.card-glint {
  position: absolute;
  top: -50%;
  left: -50%;
  width: 50px;
  height: 200px;
  background: rgba(255, 255, 255, 0.1);
  transform: rotate(45deg);
  animation: glint 4s infinite;
  pointer-events: none;
}

/* 可视化容器 */
.visualization-container {
  width: 45%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  animation: fadeInRight 1s ease-out;
}

.tech-diagram {
  height: 60%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.llm-diagram {
  width: 100%;
  height: 100%;
  max-height: 300px;
}

.diagram-circle {
  fill: none;
  stroke: #4facfe;
  stroke-width: 1;
  opacity: 0.7;
}

.outer-circle {
  animation: rotate 20s linear infinite;
  stroke-dasharray: 314;
  stroke-dashoffset: 314;
  animation: drawCircle 3s forwards, rotate 20s linear infinite 3s;
}

.middle-circle {
  animation: rotate 15s linear infinite reverse;
  stroke-dasharray: 220;
  stroke-dashoffset: 220;
  animation: drawCircle 2.5s forwards, rotate 15s linear infinite reverse 2.5s;
}

.inner-circle {
  animation: rotate 10s linear infinite;
  stroke-dasharray: 126;
  stroke-dashoffset: 126;
  animation: drawCircle 2s forwards, rotate 10s linear infinite 2s;
}

.diagram-line {
  stroke: #64ffda;
  stroke-width: 1.5;
  opacity: 0.5;
  animation: pulse-opacity 3s infinite;
}

.diagram-text {
  fill: #64ffda;
  font-size: 12px;
  text-anchor: middle;
  dominant-baseline: middle;
  font-weight: bold;
  opacity: 0;
  animation: fadeIn 1s forwards 2s;
}

/* 统计数据容器 */
.stats-container {
  margin-top: 2rem;
}

.stat-item {
  margin-bottom: 1.5rem;
}

.stat-value {
  font-size: 2rem;
  color: #64ffda;
  font-weight: 600;
}

.stat-label {
  font-size: 1rem;
  color: #8892b0;
  margin-bottom: 0.5rem;
}

.stat-bar {
  width: 100%;
  height: 8px;
  background-color: rgba(100, 255, 218, 0.1);
  border-radius: 4px;
  overflow: hidden;
}

.stat-fill {
  height: 100%;
  background: linear-gradient(90deg, #4facfe, #64ffda);
  border-radius: 4px;
  animation: fillBar 2s ease-out forwards;
  transform-origin: left;
  transform: scaleX(0);
}

/* 动画 */
@keyframes pulse {
  0% {
    transform: scale(0.8);
    opacity: 0.8;
  }
  70% {
    transform: scale(1.5);
    opacity: 0;
  }
  100% {
    transform: scale(0.8);
    opacity: 0;
  }
}

@keyframes glint {
  0% {
    left: -50%;
  }
  20%, 100% {
    left: 150%;
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeInLeft {
  from {
    opacity: 0;
    transform: translateX(-30px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes fadeInRight {
  from {
    opacity: 0;
    transform: translateX(30px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes slideInDown {
  from {
    opacity: 0;
    transform: translateY(-30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@keyframes drawCircle {
  to {
    stroke-dashoffset: 0;
  }
}

@keyframes pulse-opacity {
  0%, 100% {
    opacity: 0.3;
  }
  50% {
    opacity: 0.8;
  }
}

@keyframes fillBar {
  from {
    transform: scaleX(0);
  }
  to {
    transform: scaleX(1);
  }
}
</style> 