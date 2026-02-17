# Happy Code Year 2026

## 项目简介

Happy Code Year 2026 是一个以程序员为主题的新年祝福网页应用，为开发者们带来充满科技感和节日氛围的新年问候。

## 功能特点

- 🎉 **新年主题**：融入2026丙午马年元素，充满节日氛围
- 💻 **程序员风格**：使用代码风格的祝福语和界面设计
- 🚀 **流畅动画**：启动屏幕逐行逐字符输出效果
- 🎨 **像素艺术**：复古像素风格的标题和图标
- 📱 **响应式设计**：适配不同屏幕尺寸
- ⚡ **高性能**：使用Vue 3 + TypeScript构建，运行流畅

## 技术栈

- **前端框架**：Vue 3 + Vite
- **编程语言**：TypeScript
- **样式**：原生CSS
- **图标**：自定义SVG组件
- **动画**：CSS动画 + JavaScript控制

## 快速开始

### 环境要求

- Node.js 16.0 或更高版本
- npm 7.0 或更高版本

### 安装依赖

```bash
npm install
```

### 开发模式运行

```bash
npm run dev
```

### 构建生产版本

```bash
npm run build
```

## 项目结构

```
happy-code-year/
├── public/            # 静态资源
├── src/               # 源代码
│   ├── assets/        # 资源文件
│   ├── components/    # 组件
│   │   ├── BootScreen.vue      # 启动屏幕
│   │   ├── InvaderIcon.vue     # 像素外星人图标
│   │   └── NewYearTui.vue      # 新年祝福界面
│   ├── App.vue        # 应用根组件
│   ├── main.ts        # 应用入口
│   └── vite-env.d.ts  # Vite环境类型声明
├── index.html         # HTML模板
├── package.json       # 项目配置
├── tsconfig.json      # TypeScript配置
├── vite.config.ts     # Vite配置
└── README.md          # 项目说明
```

## 主要组件说明

### BootScreen.vue
- 启动屏幕组件，模拟命令行启动效果
- 逐行逐字符输出系统信息和新年祝福
- 包含光标闪烁和加载动画效果

### NewYearTui.vue
- 主界面组件，展示新年祝福内容
- 分为计划（Plan）和执行（Execution）两个面板
- 使用网格布局和复古风格设计

### InvaderIcon.vue
- 像素风格的外星人图标组件
- 使用SVG绘制，支持自定义大小

## 自定义配置

### 调整打字速度
在 `BootScreen.vue` 中修改 `speed` 变量：

```typescript
const speed = ref(60); // 默认速度，值越小速度越快
```

### 修改祝福语内容
在 `NewYearTui.vue` 中修改相应的文本内容，如：

```html
<div class="row">
    <span class="cb"></span><span class="cn">身体健康</span><span class="dash">—</span>
    <span class="mono">uptime: 365d, 0 crashes, 0 hotfixes</span>
</div>
```

## 部署说明

1. 执行 `npm run build` 命令构建生产版本
2. 将生成的 `dist` 目录部署到Web服务器
3. 支持GitHub Pages、Vercel、Netlify等静态网站托管服务

## 许可证

MIT License

## 致谢

- 灵感来源于程序员的日常工作和生活
- 像素风格设计参考了经典游戏元素
- 新年祝福送给所有辛勤工作的开发者们

---

**码年大吉，万事如意！** 🐴✨