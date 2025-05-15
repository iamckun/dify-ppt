<template>
  <div class="slide-content">
    <h2 class="section-title">安装和使用</h2>
    
    <div class="install-container">
      <div class="quick-start">
        <h3 class="subsection-title">快速开始</h3>
        
        <div class="requirements">
          <div class="req-title">系统要求</div>
          <div class="req-items">
            <div class="req-item">
              <div class="req-bullet"></div>
              <span>CPU >= 2核</span>
            </div>
            <div class="req-item">
              <div class="req-bullet"></div>
              <span>RAM >= 4GB</span>
            </div>
          </div>
        </div>
        
        <div class="code-block">
          <div class="code-header">
            <span>Docker Compose安装</span>
          </div>
          <pre><code># 克隆代码库
git clone https://github.com/langgenius/dify.git
cd dify

# 启动服务
docker-compose up -d</code></pre>
        </div>
      </div>
      
      <div class="usage-options">
        <h3 class="subsection-title">使用方式</h3>
        
        <div class="usage-cards">
          <div class="usage-card">
            <div class="usage-icon cloud"></div>
            <div class="usage-title">云服务选项</div>
            <div class="usage-desc">使用Dify Cloud，无需自行部署</div>
          </div>
          <div class="usage-card">
            <div class="usage-icon self-host"></div>
            <div class="usage-title">自托管社区版</div>
            <div class="usage-desc">完全控制您的数据和基础设施</div>
          </div>
          <div class="usage-card">
            <div class="usage-icon enterprise"></div>
            <div class="usage-title">企业/组织版本</div>
            <div class="usage-desc">增强的安全性和高级管理功能</div>
          </div>
        </div>
        
        <h3 class="subsection-title application-title">常见应用场景</h3>
        <div class="app-scenarios">
          <div class="app-scenario">智能客服/聊天机器人</div>
          <div class="app-scenario">文档问答系统</div>
          <div class="app-scenario">内容生成工具</div>
          <div class="app-scenario">多模型协作应用</div>
        </div>
      </div>
      
      <div class="tech-decoration">
        <div class="tech-dot dot1"></div>
        <div class="tech-dot dot2"></div>
        <div class="tech-dot dot3"></div>
        <div class="tech-line line1"></div>
        <div class="tech-line line2"></div>
      </div>
    </div>
  </div>
</template>

<script setup>
// Slide 5 - 安装和使用
</script>

<style scoped>
.slide-content {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  padding: 2rem 4rem;
  overflow: hidden;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 600;
  margin-bottom: 2rem;
  color: #64ffda;
  text-align: center;
  position: relative;
  animation: slideInDown 1s ease-out;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 100px;
  height: 3px;
  background: linear-gradient(90deg, transparent, #64ffda, transparent);
}

.install-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
  position: relative;
}

.subsection-title {
  font-size: 1.6rem;
  color: #4facfe;
  margin-bottom: 1.2rem;
  font-weight: 500;
  position: relative;
  padding-left: 1rem;
}

.subsection-title::before {
  content: '';
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 3px;
  background: #4facfe;
  border-radius: 3px;
}

.requirements {
  background: rgba(10, 25, 47, 0.6);
  border-radius: 8px;
  padding: 1rem;
  margin-bottom: 1.5rem;
  border: 1px solid rgba(79, 172, 254, 0.1);
  animation: fadeIn 0.5s ease-out 0.2s;
  animation-fill-mode: both;
}

.req-title {
  font-size: 1.1rem;
  color: #e6f1ff;
  margin-bottom: 0.8rem;
  font-weight: 500;
}

.req-items {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.req-item {
  display: flex;
  align-items: center;
  font-size: 1rem;
  color: #a8b2d1;
}

.req-bullet {
  width: 8px;
  height: 8px;
  background: #64ffda;
  border-radius: 50%;
  margin-right: 0.8rem;
}

.code-block {
  background: rgba(10, 25, 47, 0.6);
  border-radius: 8px;
  overflow: hidden;
  border: 1px solid rgba(79, 172, 254, 0.1);
  animation: fadeIn 0.5s ease-out 0.4s;
  animation-fill-mode: both;
}

.code-header {
  background: rgba(79, 172, 254, 0.1);
  padding: 0.7rem 1rem;
  font-size: 0.9rem;
  color: #e6f1ff;
  font-weight: 500;
  border-bottom: 1px solid rgba(79, 172, 254, 0.1);
}

.code-block pre {
  margin: 0;
  padding: 1rem;
  overflow-x: auto;
}

.code-block code {
  color: #a8b2d1;
  font-family: 'Fira Code', monospace;
  font-size: 0.9rem;
  line-height: 1.6;
}

.usage-cards {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
  margin-bottom: 1.5rem;
}

.usage-card {
  background: rgba(10, 25, 47, 0.6);
  border-radius: 8px;
  padding: 1.2rem;
  border: 1px solid rgba(100, 255, 218, 0.1);
  display: flex;
  flex-direction: column;
  align-items: center;
  transition: all 0.3s ease;
  animation: fadeIn 0.5s ease-out;
  animation-fill-mode: both;
}

.usage-card:nth-child(1) { animation-delay: 0.2s; }
.usage-card:nth-child(2) { animation-delay: 0.3s; }
.usage-card:nth-child(3) { animation-delay: 0.4s; }

.usage-card:hover {
  transform: translateY(-5px);
  border-color: rgba(100, 255, 218, 0.3);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

.usage-icon {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  margin-bottom: 0.8rem;
  position: relative;
}

.usage-icon::before {
  content: '';
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background: rgba(100, 255, 218, 0.1);
  animation: pulse 2s infinite alternate;
}

.usage-icon::after {
  content: '';
  position: absolute;
  width: 20px;
  height: 20px;
  top: 10px;
  left: 10px;
}

.cloud::after {
  background: linear-gradient(135deg, #64ffda, transparent);
  clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
}

.self-host::after {
  background: linear-gradient(135deg, #4facfe, transparent);
  clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%);
}

.enterprise::after {
  background: linear-gradient(135deg, #00f2fe, transparent);
  border-radius: 4px;
}

.usage-title {
  font-size: 1rem;
  color: #e6f1ff;
  margin-bottom: 0.5rem;
  font-weight: 500;
  text-align: center;
}

.usage-desc {
  font-size: 0.8rem;
  color: #a8b2d1;
  text-align: center;
  line-height: 1.4;
}

.application-title {
  margin-top: 1rem;
}

.app-scenarios {
  display: flex;
  flex-wrap: wrap;
  gap: 0.8rem;
  animation: fadeIn 0.5s ease-out 0.6s;
  animation-fill-mode: both;
}

.app-scenario {
  background: rgba(10, 25, 47, 0.6);
  border-radius: 20px;
  padding: 0.5rem 1rem;
  font-size: 0.9rem;
  color: #e6f1ff;
  border: 1px solid rgba(100, 255, 218, 0.1);
  transition: all 0.3s ease;
}

.app-scenario:hover {
  background: rgba(100, 255, 218, 0.1);
  border-color: rgba(100, 255, 218, 0.3);
  transform: scale(1.05);
}

.tech-decoration {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  pointer-events: none;
}

.tech-dot {
  position: absolute;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: #64ffda;
  opacity: 0.6;
}

.dot1 {
  top: 20%;
  left: 10%;
  animation: pulse 2s infinite alternate;
}

.dot2 {
  top: 60%;
  right: 5%;
  animation: pulse 2s infinite alternate-reverse;
}

.dot3 {
  bottom: 10%;
  left: 40%;
  animation: pulse 2s infinite alternate-reverse;
}

.tech-line {
  position: absolute;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(100, 255, 218, 0.2), transparent);
}

.line1 {
  width: 40%;
  top: 30%;
  left: 0;
  transform: rotate(-15deg);
}

.line2 {
  width: 30%;
  bottom: 40%;
  right: 0;
  transform: rotate(15deg);
}

@keyframes pulse {
  0% {
    opacity: 0.3;
    transform: scale(0.8);
  }
  100% {
    opacity: 0.6;
    transform: scale(1.2);
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

@keyframes slideInDown {
  from {
    opacity: 0;
    transform: translateY(-20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style> 