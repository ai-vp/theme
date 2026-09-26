# @hcf-ai/theme-hcf

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
pnpm add @hcf-ai/theme-hcf
# 或
npm i @hcf-ai/theme-hcf
```

### 2. 在项目根目录新建 `.npmrc`

> 用于解决 pnpm 新版本安装刚发布包与构建脚本拦截问题

```ini
minimumReleaseAge=0
ignoreBuilds=false
```

### 3. 最小化配置（推荐）

`withHcfTheme` 会自动注入 `vite.ssr.noExternal`、`optimizeDeps.exclude`，并启用 Mermaid 运行时渲染

```ts
// .vitepress/config.ts
import { withHcfTheme } from "@hcf-ai/theme-hcf/config";

export default withHcfTheme({
  title: "My Docs",
  description: "",
  themeConfig: {
    // 主题配置
  },
});
```

```ts
// .vitepress/theme/index.ts
import { theme } from "@hcf-ai/theme-hcf";
export default theme;
```

```bash
pnpm add vitepress -D
pnpm vitepress dev docs
```

## 配置项示例

```ts
export default withHcfTheme({
  title: "My Docs",
  description: "基于 @hcf-ai/theme-hcf 构建文档站点",
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
