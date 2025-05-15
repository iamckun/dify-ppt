<template>
  <div class="slide-content">
    <h2 class="section-title">总结 & Q&A</h2>
    <p class="section-subtitle">Conclusion & Q&A</p>
    
    <div class="content-container">
      <div class="key-points">
        <div class="key-points-header">
          <span class="key-icon">🔑</span>
          <span class="key-title">核心要点回顾</span>
          <span class="key-subtitle">Key Takeaways</span>
        </div>
        
        <div class="key-point-list">
          <div class="key-point-item">
            <span class="point-icon">💡</span>
            <div class="point-content">
              <span>Dify 不止于 LLM 应用开发，更是</span>
              <span class="highlight">智能伙伴</span>。
            </div>
          </div>
          
          <div class="key-point-item">
            <span class="point-icon">🚀</span>
            <div class="point-content">
              <span>精准提示工程 + 强大 RAG 能力 = </span>
              <span class="highlight">高效 AI 应用</span>。
            </div>
          </div>
          
          <div class="key-point-item">
            <span class="point-icon">🔄</span>
            <div class="point-content">
              <span>开源生态，持续迭代，提升</span>
              <span class="highlight">综合能力</span>是关键。
            </div>
          </div>
        </div>
      </div>
      
      <div class="qa-section">
        <div class="qa-header">
          <span class="qa-icon">❓</span>
          <span class="qa-title">互动交流</span>
          <span class="qa-subtitle">Q&A</span>
        </div>
        
        <div class="qa-main">
          <h3 class="qa-main-title">准备好提问了吗?</h3>
          <p class="qa-main-subtitle">Ready for Questions?</p>
        </div>
      </div>
      
      <div class="resources">
        <div class="resources-header">
          <span class="resources-icon">📚</span>
          <span class="resources-title">资源推荐</span>
          <span class="resources-subtitle">Resources</span>
        </div>
        
        <div class="resources-links">
          <a href="https://docs.dify.ai/zh-hans/introduction" target="_blank" class="resource-link">Dify 官方文档</a>
          <a href="https://github.com/langgenius/dify/discussions" target="_blank" class="resource-link">Dify Discord 社区</a>
          <a href="https://github.com/langgenius/dify" target="_blank" class="resource-link">GitHub 仓库</a>
          <a href="https://cloud.dify.ai/" target="_blank" class="resource-link">官方玩一玩</a>
        </div>
      </div>
    </div>
    
   
  </div>
</template>

<script setup>
// Slide 6 - 总结 & Q&A
</script>

<style scoped>
.slide-content {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  padding: 2rem 4rem;
  overflow: hidden;
  background-color: #0a192f;
  position: relative;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
  color: #64ffda;
  text-align: center;
  position: relative;
  animation: slideInDown 1s ease-out;
}

.section-subtitle {
  font-size: 1.2rem;
  color: #a8b2d1;
  text-align: center;
  margin-bottom: 2rem;
  opacity: 0.8;
}

.content-container {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  position: relative;
  z-index: 2;
  flex: 1;
}

/* 核心要点部分 */
.key-points {
  background: rgba(16, 33, 65, 0.5);
  border-radius: 10px;
  border: 1px solid rgba(100, 255, 218, 0.1);
  padding: 1.5rem;
  backdrop-filter: blur(10px);
  animation: fadeIn 0.5s ease-out;
}

.key-points-header {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 1rem;
  border-bottom: 1px solid rgba(100, 255, 218, 0.2);
  padding-bottom: 0.8rem;
}

.key-icon {
  font-size: 1.3rem;
}

.key-title {
  font-size: 1.2rem;
  font-weight: 600;
  color: #e6f1ff;
}

.key-subtitle {
  font-size: 0.9rem;
  color: #a8b2d1;
  margin-left: 0.5rem;
  opacity: 0.7;
}

.key-point-list {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.key-point-item {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  padding-left: 0.5rem;
}

.point-icon {
  margin-top: 0.2rem;
  font-size: 1.2rem;
}

.point-content {
  flex: 1;
  color: #e6f1ff;
  font-size: 1.1rem;
  line-height: 1.5;
}

.highlight {
  color: #64ffda;
  font-weight: 500;
}

/* 互动问答部分 */
.qa-section {
  background: rgba(16, 33, 65, 0.5);
  border-radius: 10px;
  border: 1px solid rgba(100, 255, 218, 0.1);
  padding: 1.5rem;
  margin-top: 1rem;
  text-align: center;
  animation: pulse 3s infinite alternate;
}

.qa-header {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  margin-bottom: 1.5rem;
}

.qa-icon {
  font-size: 1.3rem;
  color: #ff5470;
}

.qa-title {
  font-size: 1.2rem;
  font-weight: 600;
  color: #e6f1ff;
}

.qa-subtitle {
  font-size: 0.9rem;
  color: #a8b2d1;
  margin-left: 0.5rem;
  opacity: 0.7;
}

.qa-main {
  margin-bottom: 1rem;
}

.qa-main-title {
  font-size: 2rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
  color: #e6f1ff;
}

.qa-main-subtitle {
  font-size: 1.2rem;
  color: #a8b2d1;
}

/* 资源部分 */
.resources {
  background: rgba(16, 33, 65, 0.5);
  border-radius: 10px;
  border: 1px solid rgba(100, 255, 218, 0.1);
  padding: 1.5rem;
  position: absolute;
  right: 0;
  bottom: 3rem;
  width: 350px;
}

.resources-header {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 1rem;
  border-bottom: 1px solid rgba(100, 255, 218, 0.2);
  padding-bottom: 0.8rem;
}

.resources-icon {
  font-size: 1.2rem;
}

.resources-title {
  font-size: 1rem;
  font-weight: 600;
  color: #e6f1ff;
}

.resources-subtitle {
  font-size: 0.8rem;
  color: #a8b2d1;
  margin-left: 0.5rem;
  opacity: 0.7;
}

.resources-links {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.resource-link {
  color: #4facfe;
  font-size: 0.9rem;
  padding: 0.3rem 0;
  border-bottom: 1px dashed rgba(79, 172, 254, 0.3);
  cursor: pointer;
  transition: all 0.3s ease;
  text-decoration: none;
  display: block;
}

.resource-link:last-child {
  border-bottom: none;
}

.resource-link:hover {
  color: #64ffda;
  transform: translateX(5px);
}


.refresh-btn {
  width: 36px;
  height: 36px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  cursor: pointer;
  color: #64ffda;
  transition: all 0.3s ease;
}

.refresh-btn:hover {
  background: rgba(100, 255, 218, 0.1);
}

.nav-icon {
  width: 18px;
  height: 18px;
}

.page-indicator {
  font-size: 0.9rem;
  color: #a8b2d1;
  font-family: monospace;
  padding: 0 0.5rem;
}

/* 背景效果 */
.slide-content::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: 
    linear-gradient(to right, rgba(100, 255, 218, 0.03) 1px, transparent 1px),
    linear-gradient(to bottom, rgba(100, 255, 218, 0.03) 1px, transparent 1px);
  background-size: 30px 30px;
  z-index: 0;
  opacity: 0.4;
}

.slide-content::after {
  content: '';
  position: absolute;
  width: 300px;
  height: 300px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(100, 255, 218, 0.15) 0%, transparent 70%);
  bottom: -150px;
  right: -100px;
  z-index: 0;
  animation: float 10s infinite alternate;
}

@keyframes float {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(-20px);
  }
}

@keyframes pulse {
  0% {
    box-shadow: 0 0 5px rgba(100, 255, 218, 0.1);
  }
  100% {
    box-shadow: 0 0 20px rgba(100, 255, 218, 0.3);
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