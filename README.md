# 地平线 | Horizon

个人博客源码。记录所思所想及日常。

## 技术栈

- [Hugo](https://gohugo.io/) + [PaperMod](https://github.com/adityatelange/hugo-PaperMod) 主题
- 部署：Netlify（https://horizonzhao.netlify.app/）
- 内容：Markdown，位于 `content/`

## 本地构建

```bash
hugo server -D   # 本地预览
hugo --gc --minify  # 构建到 public/
```

## 发布流程

日常记录在知识库，每周精选成文 → 推送到本仓库 → Netlify 自动构建上线。

## 历史

本仓库 2024-09 建立，最初为 blogdown (R) 技术栈；2026-08 迁移至 Hugo。
