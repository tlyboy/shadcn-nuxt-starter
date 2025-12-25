# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 常用命令

```bash
pnpm dev        # 启动开发服务器
pnpm build      # 构建生产版本
pnpm generate   # 生成静态网站
pnpm preview    # 预览生产构建
```

## 添加 shadcn 组件

```bash
npx shadcn-vue@latest add <component-name>
```

组件会安装到 `app/components/ui/` 目录。

## 技术栈

- **框架**: Nuxt 4 + Vue 3
- **样式**: Tailwind CSS 4 (使用 Vite 插件)
- **UI 组件**: shadcn-vue (new-york 风格)
- **图标**: Iconify Carbon 图标集 + Lucide Vue Next
- **包管理器**: pnpm
- **Node 版本**: >= 22

## 项目架构

所有应用代码位于 `app/` 目录下（Nuxt 4 目录结构）:

- `app/components/ui/` - shadcn-vue UI 组件
- `app/components/` - 自定义组件
- `app/lib/utils.ts` - 工具函数（包含 `cn()` 类名合并函数）
- `app/assets/css/main.css` - 全局样式和 CSS 变量（包含明暗主题配置）
- `app/pages/` - 页面路由
- `app/layouts/` - 布局模板

## 关键配置

- **shadcn 配置**: `components.json` - 使用 TypeScript，new-york 风格，neutral 基础色
- **颜色模式**: 通过 `@nuxtjs/color-mode` 模块实现，使用 `.dark` 类切换
- **CSS 变量**: 在 `main.css` 中使用 oklch 色彩空间定义主题变量

## 样式约定

- 使用 `cn()` 函数合并 Tailwind 类名（来自 `@/lib/utils`）
- 使用 `class-variance-authority (cva)` 定义组件变体
- 深色模式通过 View Transition API 实现平滑过渡动画
