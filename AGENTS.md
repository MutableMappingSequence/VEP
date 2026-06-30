# VEP 项目规范

## 技术栈
- **静态站点**：Jekyll（GitHub Pages 部署）
- **主题**：Just the Docs（2026-06-30 从 minima 迁移）
- **包管理**：Bundler（Gemfile），使用 `github-pages` gem
- **集合**：`veps`（目录 `_veps/`，输出 `/veps/`）

## 主题 — Just the Docs

**配置要点：**
- `_config.yml` 中用 `remote_theme: just-the-docs/just-the-docs` 而非 `theme:`
- 导航通过 front matter 的 `nav_order` 控制（自动推断目录结构）
- 搜索：`search_enabled: true`
- 配色：`color_scheme`（支持 `light` / `dark`）
- `heading_anchors: true` 开启标题锚点
- `ga_tracking` 可用于 Google Analytics

**页面布局：**
- 普通页面使用 `layout: default`，添加 `nav_order` 控制侧边栏顺序
- VEP 文档使用 `_layouts/vep.html`（继承 `default` 布局）
- 侧边栏子层级通过 `parent` 和 `grand_parent` front matter 实现

**集合处理：**
- `_veps/` 中的文档由 `_layouts/vep.html` 渲染
- 集合页面不自动出现在侧边栏，通过 `veps.md` 手动展示列表

## VEP 文档规范

每篇 VEP 必须包含以下 front matter：

```yaml
---
vep: <编号>
title: <标题>
status: Draft | Accepted | Implemented | Rejected | Withdrawn | Final
type: Standard | Process | Informational
created: YYYY-MM-DD
updated: YYYY-MM-DD  # 可选
author: <作者名>      # 可选
---
```

## 代码风格

- `_config.yml` 选项按功能分组，空行分隔
- Liquid 模板尽量简洁
- 自定义 CSS 放在 `_sass/custom/custom.scss`（just-the-docs 自动加载）

## Git 提交规范

- 写完一个功能立即更新版本号并提交
- 提交信息格式：`<type>: <描述>`
- 类型：`feat` / `fix` / `style` / `refactor` / `docs`
