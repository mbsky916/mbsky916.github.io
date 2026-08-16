# AGENTS.md — 博客站点（site/）操作简版

> 完整交接文档在上级目录 `Blog/AGENTS.md`（D:\OneDrive - vip365\Hermes work\Blog\AGENTS.md），先读它。
> 本文件是 site 仓库内的简版速查。

## 事实

- 线上：https://horizonzhao.netlify.app/（push master 自动构建，约 1 分钟生效，不可撤回）
- 仓库：git@github.com:mbsky916/mbsky916.github.io.git
- Hugo：`C:\Users\zhao\AppData\Local\Microsoft\WinGet\Packages\Hugo.Hugo.Extended_Microsoft.Winget.Source_8wekyb3d8bbwe\hugo.exe`
- git 用户：mbsky916 / 970200572@qq.com

## 内容结构

- `content/posts/` — 文章（YYYY-MM-DD-主题.md，front matter：title/date/tags）
- `content/summary/` — 周总结，一年一个文件（2025.md、2026.md），`_index.md` 是年度索引
- `content/about.md`、`content/search.md` — 关于页、搜索页

## 发布流程（用户明确说"发"才执行）

1. mv 草稿（上级 `Blog/drafts/`）到 `content/posts/`
2. 构建验证：`hugo --gc --cleanDestinationDir --minify`，必须 0 ERROR
3. `git add <新文件> && git commit -m "post: <标题>" && git push origin master`
4. 等 60-90 秒，curl 线上 URL 验证 HTTP 200

## 周总结流程

- 追加到 `content/summary/<年份>.md`，格式：`## 第 XX 周（MMDD-MMDD）` + **工作：**/**生活：**/**下周：**
- 新增年份板块时更新 `_index.md`
- 素材：用户口述优先，其次每日日志（D:/OneDrive/600giteexiangmu/My libray/02-Daily/2026年/）；**不编造生活细节**

## 红线

1. 用户没说"发"绝不 push（Netlify 自动构建，不可撤回）
2. 不写公司机密、同事隐私、客户信息；不虚构事实
3. 主题名全小写匹配 themes/ 目录（Linux 构建大小写敏感）
4. 构建 0 ERROR 才算通过；hugo.toml 与 hugo.yaml 不能并存
5. 删除文件先列清单等用户确认
