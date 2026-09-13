# 地平线 | Horizon

个人博客源码，使用 Hugo 生成静态站点，记录所思所想及日常。

## 站点事实

- 当前主题：`paged`。
- 公开地址：<https://horizonzhao.netlify.app/>。
- `netlify.toml` 配置了 Netlify 构建；`.github/workflows/deploy.yml` 另定义了 GitHub Pages 部署。除非明确处理部署配置，否则不要在内容任务中切换两者。
- 内容位于 `content/`；周总结按年份保存于 `content/summary/`。

## 本地构建

```bash
hugo server -D
hugo --gc --cleanDestinationDir --minify
```

博客根目录的 `prompts/博客周总结.md` 负责周总结采集、查缺和写入决策；本站点操作边界见 [`AGENTS.md`](AGENTS.md)。

## 历史

本仓库 2024-09 建立，最初为 blogdown（R）技术栈；2026-08 迁移至 Hugo。
