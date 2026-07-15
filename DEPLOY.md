# AusDungeon 文档站部署

文档站是纯静态站点，发布目录为 `docs-site/`，自定义域名为：

```text
https://adoc.thispy.top/
```

仓库已包含：

- `docs-site/index.html`：文档首页和全部文档内容
- `docs-site/assets/`：样式、交互脚本和图标
- `docs-site/CNAME`：GitHub Pages 自定义域名
- `.github/workflows/pages.yml`：GitHub Pages 自动部署工作流

## 首次部署

1. 在 GitHub 创建仓库，例如 `AusDungeon`。
2. 将页面中的 `YOUR_NAME` 替换成你的 GitHub 用户名：
   - `docs-site/index.html` 的 GitHub 链接
   - 本文档中的仓库地址
3. 配置 Git 身份并首次推送：

```powershell
git init
git add .
git commit -m "Initial AusDungeon release and documentation"
git branch -M main
git remote add origin https://github.com/YOUR_NAME/AusDungeon.git
git push -u origin main
```

4. 打开 GitHub 仓库的 `Settings → Pages`。
5. 将 `Source` 选择为 `GitHub Actions`。
6. 等待 `Deploy AusDungeon documentation` 工作流完成。

## 自定义域名

`docs-site/CNAME` 已写入：

```text
adoc.thispy.top
```

在域名 DNS 服务商添加：

```text
类型: CNAME
主机记录: adoc
记录值: YOUR_NAME.github.io
```

如果 GitHub Pages 显示域名验证失败，先确认 DNS 已生效，再在 `Settings → Pages → Custom domain` 中填写：

```text
adoc.thispy.top
```

启用 `Enforce HTTPS` 后，最终访问地址为：

```text
https://adoc.thispy.top/
```

站点所有链接均使用根路径锚点，不依赖仓库子路径。

## 后续更新

```powershell
git add docs-site .github/workflows/pages.yml
git commit -m "Update AusDungeon documentation"
git push
```

推送到 `main` 后会自动重新部署。
