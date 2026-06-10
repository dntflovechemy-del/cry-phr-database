# 部署说明

## 方案 A：Netlify Drop，最简单

1. 打开 Netlify。
2. 登录。
3. 把整个 `cry_phr_static_web` 文件夹拖到 Netlify Drop。
4. 等待部署完成。
5. 复制生成的网址分享给别人。

## 方案 B：GitHub Pages，适合长期维护

1. 新建一个 GitHub 仓库，例如 `cry-phr-database`。
2. 上传这三个文件：
   - `index.html`
   - `cry_phr_database.csv`
   - `.nojekyll`
3. 进入仓库 `Settings` → `Pages`。
4. Source 选择 `Deploy from a branch`。
5. Branch 选择 `main`，目录选择 `/root`。
6. 保存后等待几分钟。
7. GitHub 会生成一个 `https://用户名.github.io/仓库名/` 形式的网址。

## 更新数据库

以后只需要替换仓库或部署文件夹里的：

```text
cry_phr_database.csv
```

网页代码不需要改。
