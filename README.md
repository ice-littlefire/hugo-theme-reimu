# Hugo + GitHub Pages 博客

这个仓库已经配置为使用 Hugo 和 Reimu 主题部署到 GitHub Pages。

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

文章放在 `content/post/`。新文章示例：

```powershell
hugo new content post/my-post.md
```

把文章 Front Matter 里的 `draft` 改成 `false` 后才会发布。
