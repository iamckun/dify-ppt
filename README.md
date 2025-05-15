# Dify-PPT

这是一个基于Vue 3的Dify技术分享演示项目。

## Dify技术分享PPT大纲

### 1. Dify的出现解决了什么问题，为什么选择Dify
- **LLM应用开发的挑战**
  - 开发LLM应用的技术门槛高
  - 从原型到生产的转化困难
  - 缺乏完整的开发和运维工具链
  - 模型管理与多模型集成复杂
  
- **为什么选择Dify**
  - 开源且活跃的社区（97k+ GitHub星标）
  - 低代码/无代码界面，降低开发门槛
  - 完整的LLM应用开发平台
  - 从原型到生产的一站式解决方案
  - Backend-as-a-Service模式，API快速集成

### 2. 核心能力概览
- **工作流(Workflow)**
  - 可视化画布构建AI工作流
  - 图形化界面设计与测试

- **全面的模型支持**
  - 集成数百种专有/开源LLM
  - 支持GPT系列、Mistral、Llama3等
  - 兼容任何OpenAI API的模型

- **Prompt IDE**
  - 直观的提示工程界面
  - 模型性能比较功能
  - 丰富的应用功能扩展

- **RAG流水线**
  - 文档摄取到检索的全流程支持
  - 多种文档格式支持（PDF、PPT等）
  - 自定义检索优化

- **Agent能力**
  - 基于LLM函数调用或ReAct的智能体
  - 50+内置工具（Google搜索、DALL·E等）
  - 支持自定义工具开发

- **LLMOps**
  - 应用日志与性能监控
  - 基于生产数据的持续改进
  - 提示、数据集和模型优化

- **Backend-as-a-Service**
  - 所有功能配套API
  - 轻松集成到自有业务逻辑

### 3. Dify的安装和使用
- **快速开始**
  - 系统要求（CPU >= 2核，RAM >= 4GB）
  - Docker Compose安装步骤
  - 初始化配置流程
  
- **使用方式**
  - 云服务选项（Dify Cloud）
  - 自托管社区版
  - 企业/组织版本特性
  
- **常见应用场景**
  - 智能客服/聊天机器人
  - 文档问答系统
  - 内容生成工具
  - 多模型协作应用

### 4. 总结 & Q&A
- **Dify与其他解决方案比较**
  - 与LangChain、Flowise、OpenAI Assistants的对比
  - Dify的独特优势
  
- **最佳实践**
  - 提示工程优化技巧
  - 性能调优建议
  - 生产环境部署注意事项
  
- **社区与资源**
  - GitHub、Discord社区
  - 学习资源推荐
  - 贡献与参与方式
  
- **问答环节**

## 项目结构

```
dify-ppt/
├── public/                 # 静态资源目录
│   └── favicon.ico         # 网站图标
├── src/                    # 源代码目录
│   ├── assets/             # 资源文件
│   │   ├── base.css        # 基础CSS样式
│   │   ├── main.css        # 主要CSS样式
│   │   └── logo.svg        # Logo图片
│   ├── components/         # 组件目录
│   │   └── icons/          # 图标组件
│   ├── App.vue             # 应用主组件
│   └── main.js             # 应用入口文件
├── .gitignore              # Git忽略文件
├── index.html              # HTML入口文件
├── jsconfig.json           # JavaScript配置文件
├── package.json            # 项目依赖和脚本
├── package-lock.json       # 依赖版本锁定文件
├── README.md               # 项目说明文档
└── vite.config.js          # Vite配置文件
```

## 技术栈

- 前端框架: Vue 3
- 构建工具: Vite
- 主要依赖:
  - vue: ^3.5.13
  - @vitejs/plugin-vue: ^5.2.3
  - vite: ^6.2.4
  - vite-plugin-vue-devtools: ^7.7.2

## 开发环境设置

推荐使用 [VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) 进行开发（并禁用Vetur）。

## 配置自定义设置

参考 [Vite配置文档](https://vite.dev/config/)。

## 项目设置

安装依赖:
```sh
npm install
```

### 开发模式（热重载）

```sh
npm run dev
```

### 生产环境构建

```sh
npm run build
```

### 预览生产构建

```sh
npm run preview
```

## 项目功能

本项目是一个Dify技术分享演示，用于展示Dify的各项功能和特性。
