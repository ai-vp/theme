# @ai-vp/vitepress-theme-ai

现代、优雅、可定制的 VitePress 文档主题，适合技术文档与项目站点。

- ✨ 现代设计 · 亮/暗色支持
- 🌐 多语言 · 语言跳转页
- 📑 多布局 · Home / Doc / Page / Sponsor / Changelog / Jump
- 🔍 本地搜索 · MiniSearch 集成
- 📊 Mermaid · 内置样式与快速集成

## 环境要求

- Node.js ≥ 18
- VitePress ^1.6.4

## 快速使用

### 1. 安装主题

```bash
pnpm add @ai-vp/vitepress-theme-ai
# 或
npm i @ai-vp/vitepress-theme-ai
```

### 2. 在项目根目录新建 `.npmrc`

> 用于解决 pnpm 新版本安装刚发布包与构建脚本拦截问题

```ini
minimumReleaseAge=0
ignoreBuilds=false
```

### 3. 最小化配置（推荐）

`withTheme` 会自动注入 `vite.ssr.noExternal`、`optimizeDeps.exclude`，并启用 Mermaid 运行时渲染

```ts
// .vitepress/config.ts
import { withTheme } from "@ai-vp/vitepress-theme-ai /config";

export default withTheme({
  title: "My Docs",
  description: "",
  themeConfig: {
    // 主题配置
  },
});
```

```ts
// .vitepress/theme/index.ts
import { theme } from "@ai-vp/vitepress-theme-ai ";
export default theme;
```

```bash
pnpm add vitepress -D
pnpm vitepress dev docs
```

## 配置项示例

```ts
export default withTheme({
  title: "My Docs",
  description: "基于 @ai-vp/vitepress-theme-ai  构建文档站点",
  lang: "zh-CN",
  themeConfig: {
    logo: "/logo.svg",
    nav: [
      { text: "首页", link: "/" },
      { text: "文档", link: "/guide/" },
    ],
    sidebar: {
      "/guide/": [{ text: "快速上手", link: "/guide/start" }],
    },
    search: {
      provider: "local",
    },
  },
});
```

## 内置能力

- 自动 dark / light 主题切换
- Mermaid 图表开箱即用
- 多语言路由
- 内置页面模板：Home、Changelog、Sponsor、Jump
- 本地搜索 MiniSearch
