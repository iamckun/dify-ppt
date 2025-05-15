<template>
    <div class="slide-content">
      <h2 class="section-title">核心能力概览</h2>
      
      <div class="capabilities-container">
        <div 
          v-for="(capability, index) in capabilities" 
          :key="index" 
          class="capability-card"
          :class="`card-${index+1}`"
          :style="getCardStyle(index)"
        >
          <div class="capability-icon">
            <div class="hex-icon">
              <component :is="capability.icon" class="icon" />
            </div>
          </div>
          <div class="capability-info">
            <h3 class="capability-title">{{ capability.title }}</h3>
            <p class="capability-desc">{{ capability.description }}</p>
          </div>
          <div class="card-glow"></div>
          <div class="card-connector" v-if="index < capabilities.length - 1"></div>
        </div>
      </div>
      
      <!-- 添加装饰图形 -->
      <div class="decorative-elements">
        <div class="circuit-lines"></div>
        <div class="tech-circles">
          <div class="tech-circle circle1"></div>
          <div class="tech-circle circle2"></div>
          <div class="tech-circle circle3"></div>
        </div>
        <div class="data-flow">
          <div class="data-particle" v-for="n in 20" :key="`data-${n}`"></div>
        </div>
      </div>
      
      <div class="tech-background">
        <div class="grid-lines"></div>
        <div class="floating-particles"></div>
      </div>
    
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue';
  
  // 定义SVG图标组件
  const WorkflowIcon = {
    template: `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M2 9H6V13H2V9Z" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
      <path d="M18 9H22V13H18V9Z" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
      <path d="M9 3H13V7H9V3Z" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
      <path d="M9 17H13V21H9V17Z" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
      <path d="M6 11H9M9 11V7M9 11H13M13 11V7M13 11H18M13 17V11" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>`
  };
  
  const ModelIcon = {
    template: `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M12 2L2 7L12 12L22 7L12 2Z" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
      <path d="M2 17L12 22L22 17" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
      <path d="M2 12L12 17L22 12" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>`
  };
  
  const IdeIcon = {
    template: `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M20 4L3 11L10 14L13 21L20 4Z" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
      <path d="M10 14L13 11" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>`
  };
  
  const RagIcon = {
    template: `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M8 10H4V16H8V10Z" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
      <path d="M14 4H10V16H14V4Z" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
      <path d="M20 7H16V16H20V7Z" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
      <path d="M4 20H20" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>`
  };
  
  const AgentIcon = {
    template: `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M9 21H15" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
      <path d="M12 21V17" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
      <path d="M12 17C15.866 17 19 13.866 19 10C19 6.13401 15.866 3 12 3C8.13401 3 5 6.13401 5 10C5 13.866 8.13401 17 12 17Z" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
      <path d="M8 10C8 10 10 12 12 12C14 12 16 10 16 10" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>`
  };
  
  const OpsIcon = {
    template: `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M7 7L17 17" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
      <circle cx="9" cy="15" r="2" stroke="currentColor" stroke-width="1.5"/>
      <circle cx="15" cy="9" r="2" stroke="currentColor" stroke-width="1.5"/>
      <circle cx="3.5" cy="12" r="1.5" stroke="currentColor" stroke-width="1.5"/>
      <circle cx="12" cy="3.5" r="1.5" stroke="currentColor" stroke-width="1.5"/>
      <circle cx="20.5" cy="12" r="1.5" stroke="currentColor" stroke-width="1.5"/>
      <circle cx="12" cy="20.5" r="1.5" stroke="currentColor" stroke-width="1.5"/>
    </svg>`
  };
  
  // Slide 4 - 核心能力概览
  const capabilities = ref([
    {
      title: '工作流(Workflow)',
      description: '可视化画布构建AI工作流，图形化界面设计与测试',
      icon: WorkflowIcon
    },
    {
      title: '全面的模型支持',
      description: '集成数百种专有/开源LLM，支持GPT系列、Mistral、Llama3等',
      icon: ModelIcon
    },
    {
      title: 'Prompt IDE',
      description: '直观的提示工程界面，模型性能比较功能，丰富应用功能扩展',
      icon: IdeIcon
    },
    {
      title: 'RAG流水线',
      description: '文档摄取到检索的全流程支持，多种文档格式支持（PDF、PPT等）',
      icon: RagIcon
    },
    {
      title: 'Agent能力',
      description: '基于LLM函数调用或ReAct的智能体，50+内置工具',
      icon: AgentIcon
    },
    {
      title: 'LLMOps',
      description: '应用日志与性能监控，基于生产数据的持续改进',
      icon: OpsIcon
    }
  ]);
  
  // 为卡片生成不同的位置和旋转样式
  const getCardStyle = (index) => {
    // 自定义每个卡片的位置，使它们形成不规则但有美感的分布
    const positions = [
      { left: '5%', top: '10%', rotate: '-3deg', scale: '1.05' },
      { left: '40%', top: '5%', rotate: '2deg', scale: '1' },
      { left: '75%', top: '15%', rotate: '-2deg', scale: '1.1' },
      { left: '10%', top: '55%', rotate: '3deg', scale: '1.02' },
      { left: '45%', top: '60%', rotate: '-1deg', scale: '1.08' },
      { left: '80%', top: '50%', rotate: '2deg', scale: '1' }
    ];
    
    return positions[index];
  };
  
  onMounted(() => {
    // 添加浮动粒子效果
    const particlesContainer = document.querySelector('.floating-particles');
    if (particlesContainer) {
      for (let i = 0; i < 30; i++) {
        const particle = document.createElement('div');
        particle.classList.add('particle');
        
        // 随机位置和大小
        particle.style.left = `${Math.random() * 100}%`;
        particle.style.top = `${Math.random() * 100}%`;
        particle.style.width = `${Math.random() * 4 + 1}px`;
        particle.style.height = particle.style.width;
        
        // 随机动画延迟和持续时间
        particle.style.animationDelay = `${Math.random() * 5}s`;
        particle.style.animationDuration = `${Math.random() * 10 + 10}s`;
        
        particlesContainer.appendChild(particle);
      }
    }
    
    // 添加数据流动画
    const dataFlow = document.querySelector('.data-flow');
    if (dataFlow) {
      const particles = dataFlow.querySelectorAll('.data-particle');
      particles.forEach((particle, index) => {
        // 设置随机路径和动画
        particle.style.left = `${Math.random() * 100}%`;
        particle.style.top = `${Math.random() * 100}%`;
        particle.style.animationDelay = `${Math.random() * 5}s`;
        particle.style.animationDuration = `${Math.random() * 3 + 2}s`;
      });
    }
  });
  </script>
  
  <style scoped>
  .slide-content {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    padding: 2rem 3rem;
    overflow: hidden;
    position: relative;
  }
  
  .section-title {
    font-size: 2.5rem;
    font-weight: 600;
    margin-bottom: 1rem;
    color: #64ffda;
    text-align: center;
    position: relative;
    animation: slideInDown 1s ease-out;
    z-index: 10;
  }
  
  .section-title::after {
    content: '';
    position: absolute;
    bottom: -10px;
    left: 50%;
    transform: translateX(-50%);
    width: 150px;
    height: 3px;
    background: linear-gradient(90deg, transparent, #64ffda, transparent);
  }
  
  /* 不规则排列的卡片容器 */
  .capabilities-container {
    position: relative;
    width: 100%;
    height: 85%;
    z-index: 10;
  }
  
  .capability-card {
    position: absolute;
    width: 280px;
    height: 180px;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    background: rgba(16, 33, 65, 0.6);
    border-radius: 12px;
    padding: 1.2rem;
    border: 1px solid rgba(100, 255, 218, 0.2);
    overflow: hidden;
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    transform-style: preserve-3d;
    transform: translateZ(0);
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
    text-align: center;
    animation: cardAppear 0.8s ease-out forwards;
    animation-fill-mode: both;
    opacity: 0;
  }
  
  /* 分别为每个卡片设置不同的出现延迟 */
  .card-1 { animation-delay: 0.1s; }
  .card-2 { animation-delay: 0.2s; }
  .card-3 { animation-delay: 0.3s; }
  .card-4 { animation-delay: 0.4s; }
  .card-5 { animation-delay: 0.5s; }
  .card-6 { animation-delay: 0.6s; }
  
  /* 卡片连接线 */
  .card-connector {
    position: absolute;
    z-index: -1;
    background: linear-gradient(90deg, #64ffda, transparent);
    height: 2px;
    width: 100px;
    animation: pulseConnector 2s infinite alternate;
  }
  
  .card-1 .card-connector {
    top: 70%;
    right: -100px;
    transform: rotate(20deg);
  }
  
  .card-2 .card-connector {
    bottom: 30%;
    right: -80px;
    transform: rotate(50deg);
  }
  
  .card-3 .card-connector {
    bottom: 20%;
    left: 50px;
    transform: rotate(110deg);
  }
  
  .card-4 .card-connector {
    top: 40%;
    right: -90px;
    transform: rotate(30deg);
  }
  
  .card-5 .card-connector {
    top: 30%;
    right: -110px;
    transform: rotate(10deg);
  }
  
  .capability-card:hover {
    transform: translateY(-10px) translateZ(20px) scale(1.05) !important;
    border-color: rgba(100, 255, 218, 0.6);
    box-shadow: 
      0 15px 30px rgba(0, 0, 0, 0.3),
      0 0 20px rgba(100, 255, 218, 0.3);
    z-index: 20;
  }
  
  .capability-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(135deg, transparent 85%, #64ffda 150%);
    opacity: 0.2;
    z-index: 0;
    transition: opacity 0.3s ease;
  }
  
  .capability-card:hover::before {
    opacity: 0.4;
  }
  
  .card-glow {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    background: radial-gradient(circle at center, rgba(100, 255, 218, 0.15) 0%, transparent 70%);
    opacity: 0;
    transition: opacity 0.3s ease;
    pointer-events: none;
  }
  
  .capability-card:hover .card-glow {
    opacity: 1;
  }
  
  .capability-icon {
    margin-bottom: 1rem;
    position: relative;
    z-index: 2;
  }
  
  /* 将六边形替换为不同的图标设计 */
  .card-1 .capability-icon {
    width: 70px;
    height: 70px;
    background: linear-gradient(135deg, rgba(100, 255, 218, 0.1), rgba(0, 210, 255, 0.1));
    border-radius: 12px;
    border: 1px solid rgba(100, 255, 218, 0.3);
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    overflow: hidden;
    transform: rotate(45deg);
  }
  
  .card-1 .capability-icon .icon {
    transform: rotate(-45deg);
  }
  
  .card-2 .capability-icon {
    width: 70px;
    height: 70px;
    background: rgba(100, 255, 218, 0.1);
    border-radius: 50%;
    border: 2px dashed rgba(100, 255, 218, 0.3);
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    box-shadow: 0 0 15px rgba(100, 255, 218, 0.2);
  }
  
  .card-2 .capability-icon::before {
    content: '';
    position: absolute;
    width: 80%;
    height: 80%;
    border-radius: 50%;
    border: 1px solid rgba(100, 255, 218, 0.2);
    animation: pulse 2s infinite alternate;
  }
  
  .card-3 .capability-icon {
    width: 70px;
    height: 70px;
    background: rgba(100, 255, 218, 0.05);
    clip-path: polygon(30% 0%, 70% 0%, 100% 30%, 100% 70%, 70% 100%, 30% 100%, 0% 70%, 0% 30%);
    border: 1px solid rgba(100, 255, 218, 0.3);
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
  }
  
  .card-3 .capability-icon::after {
    content: '';
    position: absolute;
    width: 40px;
    height: 40px;
    background: rgba(100, 255, 218, 0.1);
    clip-path: polygon(30% 0%, 70% 0%, 100% 30%, 100% 70%, 70% 100%, 30% 100%, 0% 70%, 0% 30%);
    animation: rotate 8s linear infinite;
  }
  
  .card-4 .capability-icon {
    width: 70px;
    height: 70px;
    background: rgba(100, 255, 218, 0.05);
    border-radius: 15px;
    border: 1px solid rgba(100, 255, 218, 0.3);
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    overflow: hidden;
  }
  
  .card-4 .capability-icon::before {
    content: '';
    position: absolute;
    width: 150%;
    height: 10px;
    background: rgba(100, 255, 218, 0.2);
    animation: scanline 3s linear infinite;
  }
  
  .card-5 .capability-icon {
    width: 70px;
    height: 70px;
    background: rgba(100, 255, 218, 0.05);
    clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);
    border: 1px solid rgba(100, 255, 218, 0.3);
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    transform-style: preserve-3d;
    perspective: 300px;
  }
  
  .card-5 .capability-icon::before,
  .card-5 .capability-icon::after {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);
    border: 1px solid rgba(100, 255, 218, 0.2);
    animation: flip3d 4s ease-in-out infinite alternate;
  }
  
  .card-5 .capability-icon::after {
    animation-delay: 2s;
  }
  
  .card-6 .capability-icon {
    width: 70px;
    height: 70px;
    background: rgba(100, 255, 218, 0.05);
    border-radius: 8px;
    border: 1px solid rgba(100, 255, 218, 0.3);
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    overflow: hidden;
  }
  
  .card-6 .capability-icon::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background: radial-gradient(circle at center, rgba(100, 255, 218, 0.3) 0%, transparent 70%);
    animation: pulse 3s infinite alternate;
  }
  
  .card-6 .capability-icon::after {
    content: '';
    position: absolute;
    width: 80%;
    height: 80%;
    border: 1px dashed rgba(100, 255, 218, 0.3);
    border-radius: 50%;
    animation: rotate 10s linear infinite;
  }
  
  .icon {
    width: 65%;
    height: 65%;
    color: #64ffda;
    transition: all 0.3s ease;
    position: relative;
    z-index: 2;
  }
  
  .capability-card:hover .icon {
    transform: scale(1.2);
    filter: drop-shadow(0 0 5px rgba(100, 255, 218, 0.5));
  }
  
  /* 删除不需要的六边形样式 */
  .hex-icon {
    display: none;
  }
  
  .capability-info {
    flex: 1;
    z-index: 1;
    display: flex;
    flex-direction: column;
    width: 100%;
  }
  
  .capability-title {
    font-size: 1.1rem;
    color: #e6f1ff;
    margin-bottom: 0.5rem;
    font-weight: 600;
    text-shadow: 0 0 10px rgba(230, 241, 255, 0.2);
  }
  
  .capability-desc {
    font-size: 0.85rem;
    color: #a8b2d1;
    line-height: 1.4;
    flex: 1;
  }
  
  /* 装饰元素 */
  .decorative-elements {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 5;
    pointer-events: none;
  }
  
  .circuit-lines {
    position: absolute;
    width: 100%;
    height: 100%;
    background-image: 
      radial-gradient(circle at 10% 20%, rgba(100, 255, 218, 0.1) 1px, transparent 1px),
      radial-gradient(circle at 90% 80%, rgba(100, 255, 218, 0.1) 1px, transparent 1px);
    background-size: 80px 80px, 120px 120px;
  }
  
  .tech-circles {
    position: absolute;
    width: 100%;
    height: 100%;
  }
  
  .tech-circle {
    position: absolute;
    border-radius: 50%;
    border: 1px dashed rgba(100, 255, 218, 0.2);
    opacity: 0.6;
  }
  
  .circle1 {
    width: 200px;
    height: 200px;
    bottom: 5%;
    left: 5%;
    animation: rotateCircle 60s linear infinite;
  }
  
  .circle2 {
    width: 300px;
    height: 300px;
    top: 10%;
    right: 5%;
    animation: rotateCircle 80s linear infinite reverse;
  }
  
  .circle3 {
    width: 150px;
    height: 150px;
    bottom: 20%;
    right: 15%;
    animation: rotateCircle 40s linear infinite;
  }
  
  .data-flow {
    position: absolute;
    width: 100%;
    height: 100%;
  }
  
  .data-particle {
    position: absolute;
    width: 3px;
    height: 3px;
    background-color: #64ffda;
    opacity: 0.7;
    border-radius: 50%;
    animation: moveParticle linear infinite;
  }
  
  /* 背景技术网格 */
  .tech-background {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
    z-index: 1;
  }
  
  .grid-lines {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: 
      linear-gradient(to right, rgba(100, 255, 218, 0.05) 1px, transparent 1px),
      linear-gradient(to bottom, rgba(100, 255, 218, 0.05) 1px, transparent 1px);
    background-size: 50px 50px;
    transform: perspective(500px) rotateX(60deg) scale(2);
    opacity: 0.3;
    transform-origin: center top;
  }
  
  .grid-lines::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    background: radial-gradient(circle at center, transparent 40%, rgba(16, 33, 65, 0.8) 100%);
    z-index: 2;
  }
  
  .floating-particles {
    position: absolute;
    width: 100%;
    height: 100%;
    overflow: hidden;
  }

  .nav-button svg {
    width: 16px;
    height: 16px;
  }
  
  @keyframes pulse {
    0% {
      opacity: 0.3;
      transform: scale(0.95);
    }
    100% {
      opacity: 0.8;
      transform: scale(1.05);
    }
  }
  
  @keyframes cardAppear {
    0% {
      opacity: 0;
      transform: translateY(30px) translateZ(-20px);
    }
    100% {
      opacity: 1;
      transform: translateY(0) translateZ(0);
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
  
  @keyframes floatParticle {
    0% {
      transform: translate(0, 0);
    }
    100% {
      transform: translate(100px, -100px);
    }
  }
  
  @keyframes rotateCircle {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }
  
  @keyframes moveParticle {
    0% {
      opacity: 0;
      transform: translate(0, 0);
    }
    50% {
      opacity: 1;
    }
    100% {
      opacity: 0;
      transform: translate(calc(100vw - 100%), calc(100vh - 100%));
    }
  }
  
  @keyframes pulseConnector {
    0% {
      opacity: 0.3;
      width: 80px;
    }
    100% {
      opacity: 0.8;
      width: 120px;
    }
  }
  
  @keyframes shimmer {
    0% {
      transform: translateX(-100%);
    }
    100% {
      transform: translateX(100%);
    }
  }
  
  @keyframes fadeIn {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
  
  /* 响应式适配 */
  @media (max-width: 768px) {
    .capability-card {
      width: 230px;
      height: 160px;
      padding: 1rem;
    }
    
    .slide-content {
      padding: 1.5rem;
    }
    
    .section-title {
      font-size: 2rem;
    }
  }
  
  /* 添加新的动画效果 */
  @keyframes scanline {
    0% {
      transform: translateY(-100%);
    }
    100% {
      transform: translateY(100%);
    }
  }
  
  @keyframes rotate {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }
  
  @keyframes flip3d {
    0% {
      transform: rotateY(0deg) scale(0.9);
    }
    100% {
      transform: rotateY(180deg) scale(1.1);
    }
  }
  </style>