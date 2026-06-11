# ice-littlefire 的学习笔记

这个仓库是我的个人学习博客，使用 Hugo 和 Reimu 主题，并通过 GitHub Actions 自动部署到 GitHub Pages。

线上地址：<https://ice-littlefire.github.io/hugo-theme-reimu/>

## 发布步骤

1. 在 GitHub 创建一个新仓库，并把本地仓库推上去。
2. 确认 `hugo.toml` 中的 `baseURL`：
   - 项目站点：`https://你的用户名.github.io/仓库名/`
   - 用户站点：`https://你的用户名.github.io/`
3. 修改 `config/_default/params.yml` 中的作者、邮箱、简介、GitHub 链接等内容。
4. 进入 GitHub 仓库的 `Settings` -> `Pages`，把 `Source` 改成 `GitHub Actions`。
5. 推送到 `main` 分支后，GitHub Actions 会自动构建并部署。

## 常用命令

```powershell
git remote add origin https://github.com/ice-littlefire/hugo-theme-reimu.git
git branch -M main
git add .
git commit -m "Create Hugo blog with Reimu theme"
git push -u origin main
```

## 本地预览

本机目前没有安装 Hugo。安装 Hugo Extended 后可以运行：

```powershell
git clone --depth 1 --branch v0.16.0 https://github.com/D-Sketon/hugo-theme-reimu.git themes/reimu
hugo server -D
```

如果 `themes/reimu` 已经存在，就不用重复克隆。

## 写文章

文章放在 `content/post/`。建议按“系列或主题 + 编号 + 简短英文标题”的方式命名，后面文章多了也容易查找。

示例：

```text
zero-to-fullstack-02-03-how-the-internet-works.md
codex-bilibili-auto-notes-tool.md
```

新文章可以手动创建 Markdown 文件，也可以使用 Hugo 命令：

```powershell
hugo new content post/my-post.md
```

把文章 Front Matter 里的 `draft` 改成 `false` 后才会发布。

如果某一类文章越来越多，可以再按文件夹整理，例如：

```text
content/post/zero-to-fullstack/
content/post/projects/
content/post/notes/
```

不过文章数量少的时候，先放在 `content/post/` 下更简单。
