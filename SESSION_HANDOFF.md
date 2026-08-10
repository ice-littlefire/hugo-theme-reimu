# 博客项目交接说明

这份文件用于防止会话信息丢失。下次新开 Codex 对话时，可以直接把这份内容发给 Codex，让它接着处理博客。

## 基本信息

- 本地目录：`D:\demo_\web`
- GitHub 用户名：`ice-littlefire`
- GitHub 仓库：`https://github.com/ice-littlefire/hugo-theme-reimu`
- 线上博客：`https://ice-littlefire.github.io/hugo-theme-reimu/`
- 技术栈：Hugo + GitHub Pages + GitHub Actions
- 主题：Reimu，构建时从 `D-Sketon/hugo-theme-reimu` 拉取
- 当前分支：`main`

## 当前状态

- GitHub Pages 的 Source 已设置为 `GitHub Actions`。
- 推送到 `main` 后，GitHub Actions 会自动构建并部署。
- 仓库当前是干净状态，本地 `main` 与远端 `origin/main` 一致。
- 最近一次提交是回退提交：`b794da9 Revert "Polish blog content and navigation"`。
- 这次回退撤销了不满意的博客美化改动，但保留了之前的文章、头像和音乐播放器配置。

## 已完成事项

- 搭建 Hugo 博客并配置 GitHub Pages 自动部署。
- 使用 Reimu 主题。
- 设置博客头像为用户提供的 `avatar.webp`。
- 作者名改为 GitHub 用户名：`ice-littlefire`。
- 添加文章：
  - `content/post/zero-to-fullstack-02-03-how-the-internet-works.md`
  - `content/post/codex-bilibili-auto-notes-tool.md`
  - `content/post/hello-world.md`
- 给“零到全栈 2.3”文章添加了 B 站原视频来源链接。
- 复现了 Reimu demo 的音乐播放器功能配置。

## 关键文件

- `hugo.toml`：站点基础配置，包含 `baseURL`、站点标题、主题名等。
- `config/_default/params.yml`：Reimu 主题配置，包含作者、头像、菜单、播放器等。
- `.github/workflows/hugo.yaml`：GitHub Actions 部署流程。
- `static/avatar/avatar.webp`：当前头像。
- `content/post/`：博客文章目录。
- `data/friends.yml`：友链数据。
- `README.md`：博客发布和写文章说明。

## 音乐播放器配置

音乐播放器配置在 `config/_default/params.yml`。

当前做法是启用：

- `pjax.enable: true`
- `player.aplayer.enable: true`
- `player.meting.enable: true`
- 网易云歌单：`id: 2265921590`
- `server: netease`
- `type: playlist`

注意：如果页面上有播放器但歌曲加载失败，通常是网易云/Meting 接口或版权限制，不一定是 Hugo 配置错。必要时可以改成手动配置音频直链。

## 文章命名建议

目前文章先放在 `content/post/` 下即可。

建议命名方式：

```text
series-or-topic-xx-xx-short-title.md
```

示例：

```text
zero-to-fullstack-02-03-how-the-internet-works.md
codex-bilibili-auto-notes-tool.md
```

以后文章多了，可以再按类型建文件夹：

```text
content/post/zero-to-fullstack/
content/post/projects/
content/post/notes/
```

## 最近提交记录

```text
b794da9 Revert "Polish blog content and navigation"
512ff3c Polish blog content and navigation
bf9e8ec Enable music player
9a4cf98 Add post about Bilibili auto notes tool
087c08a Add Bilibili source link to internet post
4f9f1e0 Add source link and normalize post filename
039dd61 添加关于互联网工作原理的文章
8533470 Use custom avatar image
```

## 用户偏好

- 用户是博客和 GitHub Pages 初学者，需要步骤清楚、少术语。
- 用户常用 VS Code 的“源代码管理 / 同步更改”来推送。
- 不喜欢一次性大改博客风格。后续应该小范围、可控地调整。
- 博客内容主要来自 B 站学习视频笔记，建议在文章末尾保留“来源”或“参考”链接。
- 图片可以使用外链，用户觉得这样比较方便。

## 下次继续时的建议

如果继续完善博客，建议不要再一次性大面积改动。可以从这几个小点里选一个做：

1. 只优化“关于”页文案。
2. 只优化首页标题和副标题。
3. 只整理文章分类和标签。
4. 只调整音乐播放器配置。
5. 只新增一篇文章。

每次改完后建议执行：

```powershell
git status --short --branch
git add .
git commit -m "说明本次改动"
git push
```

推送后等待 GitHub Actions 自动部署，通常 1 到 3 分钟生效。
