# 站点仓库 Agent 规则

## 适用范围与事实

本文件只补充 `site/` 独立 Git 仓库的站点操作；博客根目录的通用规则和周总结采集流程按需使用上级文件。

- 内容：`content/posts/` 为文章，`content/summary/` 为按年份保存的周总结，`content/summary/_index.md` 为总结索引。
- 根配置：`hugo.yaml`；当前主题为 `paged`。不要另建同级 `hugo.toml`。
- Hugo 可执行文件：`C:\Users\zhao\AppData\Local\Microsoft\WinGet\Packages\Hugo.Hugo.Extended_Microsoft.Winget.Source_8wekyb3d8bbwe\hugo.exe`。
- `netlify.toml` 配置 Netlify 构建；`.github/workflows/deploy.yml` 另定义了 GitHub Pages 部署。内容任务不切换、删除或重写部署目标。

## 本地内容操作

- 用户明确要求修改时，直接编辑目标文件并做必要检查，不为安全的本地步骤逐项等待确认。
- 周总结候选内容必须先展示；只有用户明确说“写入本周总结”或“保存”后，才更新 `content/summary/<年份>.md`，并同步已有索引格式。写入不触发提交或推送。
- 写入前检查目标周是否已存在，写入后检查标题、三节内容、重复周和文件状态。失败就修复后重查。

## 构建与发布

- 本地构建命令：`hugo --gc --cleanDestinationDir --minify`，在仓库根目录执行并确认无错误。
- 只有用户明确说“发/发布博客”时，才执行 `git add`、提交和 `git push origin master`。提交只包含本次任务文件。
- 推送后验证公开地址 <https://horizonzhao.netlify.app/>；没有成功响应时如实报告，不把本地构建当成线上发布成功。

## 安全边界

- 不写入公司机密、同事隐私、客户信息或未经确认的敏感细节；不编造素材。
- 不批量删除或递归清理文件。删除时只处理用户明确指定的单个路径，并保留无关改动。
